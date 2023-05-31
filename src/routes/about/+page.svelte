<script lang="ts">
  import Animate from "$components/atoms/Animate.svelte";

  import { fade, fly } from "svelte/transition";
  import { quintOut } from "svelte/easing";

  const birthday = import.meta.env.VITE_BIRTHDAY;
  const getAge = () => {
    const ageDifMs = Date.now().valueOf() - new Date(birthday).valueOf();
    const ageDate = new Date(ageDifMs);
    return Math.abs(ageDate.getUTCFullYear() - 1970);
  };
</script>

<svelte:head>
  <title>About</title>
  <meta name="description" content="Zain Omran's Portfolio site about me page." />
</svelte:head>

<div
  class="flex h-screen flex-col items-center justify-center md:px-8 lg:ml-11 lg:max-w-full lg:flex-row xl:ml-0"
>
  <Animate>
    <div class="overflow-hidden px-4 md:overflow-auto">
      <img
        transition:fly|local={{ x: 50, duration: 500, easing: quintOut }}
        class="aspect-auto rounded-lg shadow-md transition-all duration-200 sm:max-w-sm lg:mr-10 lg:grayscale lg:hover:grayscale-0"
        src="/images/1.png"
        alt="Graduation Event"
      />
    </div>
    <div class="flex max-w-md flex-col flex-wrap items-center justify-center lg:items-start">
      <h1
        transition:fade|local={{ delay: 100, duration: 800, easing: quintOut }}
        class="my-5 text-3xl font-bold text-neutral backdrop-blur-sm lg:my-0 lg:mb-5 lg:text-5xl xl:text-6xl"
      >
        Zain Omran
      </h1>
      <p
        transition:fade|local={{ delay: 100, duration: 800, easing: quintOut }}
        class="font-secondary text-md px-8 text-center leading-6 text-accent backdrop-blur-sm lg:px-0 lg:text-left lg:text-lg lg:leading-normal xl:text-xl"
      >
        Hey, I'm Zain, a highly motivated full stack developer who is always eager to learn and grow. 
        With my expertise in both front-end and back-end development, I am confident in my ability to create innovative and 
        efficient solutions for any project. Slide in my email and let's get in touch!
      </p>
    </div>
  </Animate>
</div>
