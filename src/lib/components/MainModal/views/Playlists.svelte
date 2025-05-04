<script>
  import { songs } from "../../../temp/songs";
  import { Label, Switch } from "bits-ui";

  const playlistNames = [
    "Morning Coffee Vibes",
    "Chill Evening Acoustic",
    "Road Trip Essentials",
    "Friday Night Party Mix",
    "Sunday Morning Soul",
    "Workout Motivation 2024",
    "Focus Flow Instrumentals",
    "Relaxing Spa Music",
    "Summer Beach Jams",
    "Throwback 90s Hip Hop",
    "Indie Rock Anthems",
    "Classical Focus",
    "Happy Hits for You",
    "Best of 2000s Pop",
    "Latin Dance Fiesta",
  ];
</script>

<div class="w-full h-full flex flex-col gap-0.5 text-neutral-100 text-xs">
  <div
    class="w-full gap-0.5 pt-0.5 flex-wrap flex h-10f max-h-16 overflow-hidden bg-neutral-900f radius-defaultf border-bf border-neutral-700"
  >
    {#each playlistNames as playlist}
      <div
        class="text-basef p-1.5 cursor-pointer hover:bg-neutral-700 bg-container-2f border border-neutral-600 font-semibold text-nowrap overflow-hidden text-ellipsis max-w-40"
      >
        {playlist}
      </div>
    {/each}
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
    class="w-full flex text-neutral-400 justify-between items-center h-10f px-2 py-1.5 bg-neutral-900f radius-defaultf border-bf border-neutral-700"
  >
    <div>
      <p>34 items</p>
    </div>
    <div class="flex items-center">
      <button type="button" class="mr-2">Remember position</button>
      <Switch.Root
        id="dnd"
        name="hello"
        class="focus-visible:ring-neutral-200 focus-visible:ring-offset-background data-[state=checked]:bg-accent-1 data-[state=unchecked]:bg-neutral-600 data-[state=unchecked]:shadow-mini-inset dark:data-[state=checked]:bg-accent-1 focus-visible:outline-hidden peer inline-flex h-4 w-8 shrink-0 cursor-pointer items-center rounded-full px-[3px] transition-colors focus-visible:ring-2 focus-visible:ring-offset-2 disabled:cursor-not-allowed disabled:opacity-50"
      >
        <Switch.Thumb
          class="bg-neutral-200 data-[state=unchecked]:shadow-mini dark:bg-foreground dark:shadow-popover pointer-events-none block size-3 shrink-0 rounded-full transition-transform data-[state=checked]:translate-x-3.5 data-[state=unchecked]:translate-x-0"
        />
      </Switch.Root>
    </div>
  </div>
</div>
