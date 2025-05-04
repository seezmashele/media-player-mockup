<script>
  import {
    CircleXIcon,
    FolderIcon,
    InfoIcon,
    ListVideoIcon,
    Maximize2Icon,
    Minimize2Icon,
    SettingsIcon,
    SquarePlayIcon,
  } from "@lucide/svelte";
  import NowPlaying from "./views/NowPlaying.svelte";
  import Playlists from "./views/Playlists.svelte";
  import Settings from "./views/Settings.svelte";
  let currentView = $state("now-playing");
  let isMinimized = $state(false);

  $effect(() => {
    console.log("currentView: ", currentView);
  });
</script>

<div
  onclick={(e) => {
    e.stopPropagation();
  }}
  class="w-full pointer-events-auto m-2 flex h-full gap-0.5 max-w-[960px]f max-h-[680px] border border-neutral-700 bg-neutral-800"
>
  <div
    class="w-9 flex-shrink-0 text-neutral-400 flex flex-col justify-between h-full bg-container-2 bg-opacity-9 border-neutral-700"
  >
    <div>
      <button
        type="button"
        class={`drawer-button radius-default`}
        onclick={() => {
          console.log("close modal");
        }}
      >
        <CircleXIcon class="icon-size-default text-neutral-400" />
      </button>
      <div class="h-9 w-full"></div>
      <button
        type="button"
        class={`drawer-button radius-default ${
          currentView === "now-playing" && "drawer-button-active"
        }`}
        onclick={() => {
          currentView = "now-playing";
        }}
      >
        <SquarePlayIcon class="icon-size-default " />
      </button>
      <button
        type="button"
        class={`drawer-button radius-default ${
          currentView === "playlists" && "drawer-button-active"
        }`}
        onclick={() => {
          currentView = "playlists";
        }}
      >
        <ListVideoIcon class="icon-size-default text-neutral-400" />
      </button>
      <button
        type="button"
        class={`drawer-button radius-default ${
          currentView === "settings" && "drawer-button-active"
        }`}
        onclick={() => {
          currentView = "settings";
        }}
      >
        <SettingsIcon class="icon-size-default" />
      </button>
    </div>
    <div class="w-full">
      <button
        type="button"
        class={`drawer-button radius-default`}
        onclick={() => {
          isMinimized = !isMinimized;
        }}
      >
        {#if isMinimized}
          <Maximize2Icon class="icon-size-default text-neutral-400" />
        {:else}
          <Minimize2Icon class="icon-size-default text-neutral-400" />
        {/if}
      </button>
      <button
        type="button"
        class={`drawer-button radius-default ${
          currentView === "settings" && "drawer-button-active"
        }`}
        onclick={() => {
          currentView = "info";
        }}
      >
        <InfoIcon class="icon-size-default text-neutral-400" />
      </button>
    </div>
  </div>
  <div class="w-full h-full">
    {#if currentView === "now-playing"}
      <NowPlaying />
    {/if}
    {#if currentView === "playlists"}
      <Playlists />
    {/if}
    {#if currentView === "settings"}
      <Settings />
    {/if}
  </div>
</div>
