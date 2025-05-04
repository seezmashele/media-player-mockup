<script>
  import { songs } from "../../../temp/songs";
</script>

<div class="w-full h-full text-neutral-100 text-xs">
  <div
    class="w-full h-10 p-0.5 bg-neutral-900f radius-defaultf border-bf border-neutral-700"
  ></div>
  <div class="overflow-y-auto flex flex-col gap-0.5 h-full bg-purple-300f">
    {#each songs as song}
      <div
        class="w-full p-1.5 cursor-pointer bg-item-container hover:bg-item-container-hover"
      >
        {song.title}
      </div>
    {/each}
  </div>
</div>
