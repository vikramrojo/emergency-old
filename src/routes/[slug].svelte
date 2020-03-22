<script context="module">
  export async function preload({ params, query }) {
    // the `slug` parameter is available because
    // this file is called [slug].svelte
    const res = await this.fetch(`${params.slug}.json`);
    const data = await res.json();

    if (res.status === 200) {
      return { post: data };
    } else {
      this.error(res.status, data.message);
    }
  }
</script>

<script>
  import PostInfo from "./postInfo.svelte";
  export let post;
</script>

<style>

</style>

<svelte:head>
  <title>{post.data.title}</title>
</svelte:head>

<div class="">

  <h1 class="">{post.data.title}</h1>
  <PostInfo {post} />
  <div class="">
    {@html post.content}
  </div>
</div>
