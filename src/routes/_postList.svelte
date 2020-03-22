<script>
  import PostListView from "./_postListView.svelte";
  import { posts, tagFilter } from "../store.js";
  //   console.log($tagFilter);
</script>

<h2 class="">Resources {$tagFilter ? 'on ' + $tagFilter : ''}</h2>

<ul grid columns="3" gap="2">
  {#each $posts as post}
    <li cell>
      <PostListView {post} />
    </li>
  {/each}
</ul>
