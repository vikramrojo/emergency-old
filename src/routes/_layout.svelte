<script>
  import Sidebar from "./_sidebar.svelte";
  export let segment;
</script>

<main p="8" class="">
  <Sidebar {segment} />

  <slot />
</main>
