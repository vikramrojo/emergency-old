<script>
  import PostListView from "./_postListView.svelte";
  import { posts, tagFilter } from "../store.js";
  //   console.log($tagFilter);
</script>

<div class="">Recent posts {$tagFilter ? 'about ' + $tagFilter : ''}</div>

<ul>
  {#each $posts as post}
    <li>
      <PostListView {post} />

    </li>
  {/each}
</ul>
