<script lang="ts">
  import Icon from "@iconify/svelte";

  export let href: string;
</script>

<a
  {href}
  class="group flex h-9 w-24 items-center justify-center rounded-md bg-secondary/20 text-secondary no-underline backdrop-blur-sm transition-colors hover:bg-neutral hover:text-primary focus:text-primary focus:outline-none hover:dark:text-secondary focus:dark:text-secondary"
>
  <div class="transition-transform group-hover:-translate-x-1">
    <Icon height="30" width="30" icon="eva:arrow-back-outline" />
  </div>
  <div>
    <p
      class="-translate-y-[1px] text-sm font-semibold text-secondary transition-colors group-hover:text-primary group-focus:text-primary group-hover:dark:text-secondary group-focus:dark:text-secondary"
    >
      Back
    </p>
  </div>
</a>
