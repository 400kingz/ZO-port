<script lang="ts">
  import "$src/app.postcss";

  import ActionButtons from "$components/molecules/ActionButtons.svelte";
  import Navbar from "$components/organisms/Navbar.svelte";

  import { Toaster } from "svelte-french-toast";
</script>

<svelte:head>
  <link rel="preload" as="image" href="/images/1.png" />
</svelte:head>

<Toaster />
<Navbar />
<ActionButtons />
<slot />
