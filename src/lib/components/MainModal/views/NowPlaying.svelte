<script>
  import { FolderIcon } from "@lucide/svelte";
  import { songs } from "../../../temp/songs";
</script>

<div class="w-full h-full flex flex-col text-neutral-100 text-xs">
  <div
    class="w-full h-10 flex items-center p-0.5 px-2 bg-neutral-900f radius-defaultf border-bf border-neutral-700"
  >
    <h2 class="text-basef font-semibold mr-2">Now playing:</h2>
    <FolderIcon class="w-4 h-4 mr-2" /> Videos
  </div>
  <div
    class="overflow-y-auto mr-0.5 pr-0.5 flex flex-col gap-0.5 h-full bg-purple-300f"
  >
    {#each songs as song}
      <div
        class="w-full p-2 cursor-pointer bg-item-container hover:bg-item-container-hover"
      >
        {song.title}
      </div>
    {/each}
  </div>
  <div
    class="w-full flex justify-between items-center h-10 p-0.5 bg-neutral-900f radius-defaultf border-bf border-neutral-700"
  >
    <div>
      <p>34 items</p>
    </div>
    <div></div>
  </div>
</div>
