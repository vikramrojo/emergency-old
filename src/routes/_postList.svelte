<script>
  import PostListView from "./_postListView.svelte";
  import { posts, tagFilter } from "../store.js";
  //   console.log($tagFilter);
</script>

<h2 class="">Resources {$tagFilter ? 'on ' + $tagFilter : ''}</h2>

<ul grid columns="3" gap="6">
  {#each $posts as post}
    <li cell p="6" shadow="3" bg="white">
      <PostListView {post} />
    </li>
  {/each}
</ul>
