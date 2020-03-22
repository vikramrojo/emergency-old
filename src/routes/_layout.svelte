<script>
  import Header from "./_header.svelte";
  import Footer from "./_footer.svelte";
  export let segment;
</script>

<main flex="column" justify="between">
  <section>
    <Header {segment} />
    <slot />
  </section>
  <Footer />
</main>

<style>
main {
  height: 100vh;
  
}
</style>