<script>
  import {
    CircleXIcon,
    ListVideoIcon,
    SettingsIcon,
    SquarePlayIcon,
  } from "@lucide/svelte";
  import NowPlaying from "./views/NowPlaying.svelte";
  import Playlists from "./views/Playlists.svelte";
  import Settings from "./views/Settings.svelte";
  let currentView = $state("now-playing");

  //   $useEffect(() => {
  //     console.log("currentView: ", currentView);
  //   });
</script>

<div
  class="w-full flex h-full gap-0.5 max-w-[960px] max-h-[540px] border border-neutral-700 bg-neutral-800"
>
  <div
    class="w-10 text-neutral-400 flex flex-col justify-centerf h-full bg-drawer-container bg-opacity-10 border-neutral-700"
  >
    <button
      type="button"
      class={`drawer-button radius-default`}
      onclick={() => {
        console.log("close modal");
      }}
    >
      <CircleXIcon class="icon-size-default text-neutral-400" />
    </button>
    <div class="h-10 w-full"></div>
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
      <SettingsIcon class="icon-size-default text-neutral-400" />
    </button>
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
