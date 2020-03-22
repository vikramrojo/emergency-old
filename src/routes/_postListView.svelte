<script>
  import PostInfo from "./postInfo.svelte";
  export let post;
</script>

<div class="">
  <a class="" rel="prefetch" href={post.data.slug}>
    <h2>{post.data.title}</h2>
  </a>
  <PostInfo {post} />
  <div class="">
    {@html post.excerpt}
  </div>
</div>
