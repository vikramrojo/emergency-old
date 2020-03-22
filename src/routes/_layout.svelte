<script>
  import Sidebar from "./_sidebar.svelte";
  export let segment;
</script>

<div class="">
  <!-- intermediary wrapper -->
  <div class="">
    <!-- sidebar -->
    <Sidebar {segment} />
  </div>

  <!-- non-sidebar -->
  <main class="">
    <slot />
  </main>
</div>
