<script lang="ts">
  import Animate from "$components/atoms/Animate.svelte";

  import { fade, fly } from "svelte/transition";
  import { quintOut } from "svelte/easing";

  export let styles = "";
  export let title: string;
  export let footer: string;
  export let current: boolean;
  export let url: string = "";
</script>

<Animate>
  <div
    class="indicator flex max-h-max w-full flex-col justify-between rounded-xl border border-secondary/20 bg-secondary/5 p-4 backdrop-blur-sm transition-transform duration-200 dark:bg-secondary/10 sm:max-h-[15rem] md:max-h-[23rem] md:max-w-[35rem] lg:min-h-full lg:hover:-translate-y-0.5"
    transition:fly|local={{ y: 50, duration: 500, easing: quintOut }}
  >
    {#if current}
      <span class="badge-neutral badge indicator-item" />
    {/if}
    <div>
      {#if title}
        <h2 class="underline-offset-7 text-md mb-3 font-bold leading-6 text-neutral">
          <a href={url}>{title}</a>
        </h2>
      {/if}
      <div
        class={`flex flex-wrap justify-center text-sm leading-6 text-secondary ${styles}`}
        transition:fade|local={{ delay: 150, duration: 800, easing: quintOut }}
      >
        <slot />
      </div>
    </div>
    {#if footer}
      <div class="mt-2" in:fade={{ delay: 200, duration: 800, easing: quintOut }}>
        <div class="divider m-0 before:bg-secondary/20 after:bg-secondary/20" />
        <p class="pt-1 text-xs font-semibold">
          {footer}
        </p>
      </div>
    {/if}
  </div>
</Animate>
