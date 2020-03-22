<script>
  import PostInfo from "./postInfo.svelte";
  export let post;
</script>

<div class="">
  <a class="" rel="prefetch" href={post.data.slug}>{post.data.title}</a>
  <PostInfo {post} />
  <div class="">
    {@html post.excerpt}
    <br />
    <div class="">
      <a href={post.data.slug}>Read more...</a>
      <i class="" />
    </div>
  </div>
</div>
