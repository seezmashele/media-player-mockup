<script>
  import { Slider } from "bits-ui";
  let sliderValue = $state(50);
  import cn from "clsx";
  import MainModal from "./lib/components/MainModal/MainModal.svelte";
</script>

<main
  class="w-screen bg-neutral-500 p-12 h-screen flex items-center justify-center"
>
  <div
    class="w-full h-full max-w-[1280px] max-h-[720px] bg-neutral-900 borderf border-neutral-400 shadow-lg"
  >
    <div class="h-full flex w-full items-end flex-col">
      <div
        class="w-full p-5 bg-purple-700f borderf border-yellow-500f flex items-center justify-center h-full"
      >
        <MainModal />
      </div>
      <div class="w-full bg-neutral-800 border-t border-neutral-700">
        <div class="w-full p-2">
          <Slider.Root
            type="single"
            class="relative flex w-full touch-none select-none items-center"
          >
            {#snippet children()}
              <span
                class="bg-neutral-700 relative h-1.5 w-full grow cursor-pointer overflow-hidden rounded-full"
              >
                <Slider.Range class="bg-accent-1 absolute h-full" />
              </span>
              <Slider.Thumb
                index={0}
                class={cn(
                  "border-neutral-400 bg-neutral-400 hover:border-dark-40 focus-visible:ring-foreground dark:bg-foreground dark:shadow-card focus-visible:outline-hidden block size-3 cursor-pointer rounded-full border shadow-sm transition-colors focus-visible:ring-0 focus-visible:ring-offset-2f activef:scale-[0.98]f disabled:pointer-events-none disabled:opacity-50"
                )}
              />
            {/snippet}
          </Slider.Root>
        </div>
        <div
          class="w-full text-xs text-neutral-100 bg-neutral-900 px-2 py-1 flex justify-between"
        >
          <p class="">Playing [HW]</p>
          <p>00:00</p>
        </div>
      </div>
    </div>
  </div>
</main>
