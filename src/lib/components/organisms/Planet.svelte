<script lang="ts">

  import { onMount, onDestroy } from 'svelte';
  import * as THREE from 'three';
  import HALO from 'vanta/dist/vanta.halo.min';

  let container: HTMLElement;

  let vantaEffect: any = null;


  const setVantaSize = () => {
    if (vantaEffect) {
      vantaEffect.setSize(window.innerWidth, window.innerHeight);
    }
  };

  onMount(() => {
    let minHeight, minWidth;
    
    if (window.innerWidth < 600) {  // for example, for mobile devices
      minHeight = 480;
      minWidth = 320;
    } else {
      minHeight = window.innerHeight;
      minWidth = window.innerWidth;
    }

    vantaEffect = HALO({
      el: container,
      THREE: THREE,
      mouseControls: true,
      touchControls: true,
      gyroControls: true,
      baseColor: 0x006eff,
      backgroundColor: 0x484848,
      xOffset: -0.20,
      amplitudeFactor: 1.50,
      speed: 1.90,
      minHeight: minHeight,
      minWidth: minWidth,
    });

    window.addEventListener('resize', setVantaSize);
  });

  onDestroy(() => {
    if (vantaEffect) {
      vantaEffect.destroy();
    }

    window.removeEventListener('resize', setVantaSize);
  });



</script>


<div class="container">
  <div bind:this={container} class="planet" />
</div>




<style>
  .planet {
      position: absolute;
      top: 0;
      left: 0;
      z-index: -1;
  }
  @media (max-width: 600px) {
    .planet {
      width: 100vw;
      height: 100vh;
    }
  }


</style>