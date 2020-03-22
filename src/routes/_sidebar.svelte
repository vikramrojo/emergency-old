<script>
  export let segment;
  import { tags, tagFilter } from "../store.js";
  import { goto } from "@sapper/app";
  function filterByTag(tag) {
    tagFilter.set({ tag: tag });
  }

  function clearTagFilter() {
    tagFilter.set({});
  }
</script>

<div class="">

  <a class={segment === undefined ? '' : ''} href=".">Home</a>

  <a class={segment === 'about' ? '' : ''} href="about">About</a>

  <div class="">

    <!-- If we have at least 2 tags, add option to remove filter -->
    {#if $tags.length > 2}
      <a class="" href="/">all</a>
    {/if}

    {#each $tags as tag}
      <a class="" href="/?tag={tag}">{tag}</a>
    {/each}
  </div>

</div>
