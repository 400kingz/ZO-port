<script>
  import { onMount, onDestroy } from "svelte";
  import { afterUpdate } from "svelte";
  import Button from "$components/atoms/Button.svelte";
  import { fly } from "svelte/transition";
  import { quintOut } from "svelte/easing";

  let showPopUp = true;
  let isMobile = false;

    // dont show popup on larger than mobile views
    if (window.innerWidth < 640) {
        isMobile = true;
        }

  const hidePopUp = () => {
    showPopUp = false;
  };

  onMount(() => {
    const handleTap = () => {
      hidePopUp();
      document.removeEventListener("touchstart", handleTap);
    };

    document.addEventListener("touchstart", handleTap);
  });

  onDestroy(() => {
    hidePopUp();
  });

  afterUpdate(() => {
    if (showPopUp) {
      setTimeout(hidePopUp, 5000); // Hide the pop-up after 3 seconds
    }
  });
</script>

{#if showPopUp && isMobile}
    <div
        transition:fly|local={{ x: 50, delay: 100, duration: 500, easing: quintOut }}
        class="fixed z-50 flex items-center justify-center w-full h-full ">
    <Button on:click={hidePopUp}>
            <p>Tap around</p>
        </Button>
    </div>
{/if}

<style>
    div {
        bottom: 20%;
    }
</style>
