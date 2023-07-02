<script lang="ts">

  import Animate from "$components/atoms/Animate.svelte";
  import Button from "$components/atoms/Button.svelte";
  import Planet from "$components/organisms/Planet.svelte";

  import { fade, fly } from "svelte/transition";
  import { quintOut } from "svelte/easing";

  import Popup from "$components/molecules/Popup.svelte";
</script>

<svelte:head>
  <title>Zain's Portfolio</title>
  <meta name="description" content="Zain Omran's Portfolio site home page." />
</svelte:head>



<Animate>

  <Planet />
  

  <div
    transition:fade|local={{ duration: 800, easing: quintOut }}
    class="flex h-screen w-full flex-col items-center justify-center px-5 lg:items-end lg:px-32"
  >

    <h2
      class="font-secondary mb-0 text-center text-2xl font-bold text-accent sm:mb-1 sm:text-4xl sm:font-bold md:text-right"
    >
      Hi, my name is
    </h2>
    <h1
      class="font-primary z-10 mb-2 mt-1 text-center text-3xl font-bold text-neutral sm:text-5xl md:text-right lg:text-7xl"
    >
      Zain Omran
    </h1>
    <h1
      class="py-1 text-center text-3xl text-neutral md:text-right lg:text-[3.05rem]"
    >
      self taught dev but the good kind.
    </h1>
    <div class="mt-5" transition:fly|local={{ x: 50, delay: 100, duration: 500, easing: quintOut }}>
      <Button href="/work">Check Out My Work</Button>
      
    </div>
    <Popup />
  </div>
</Animate>

<style>
  Popup {
    top: 50%;
  }
  /* add proper css for the Planet element so that it is the background */
</style>


