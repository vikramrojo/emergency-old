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

<div mb="3">

  <h1>
    <a class={segment === undefined ? '' : ''} href=".">sub.emergency.fyi</a>
  </h1>
  A community sourced resource that highlights active efforts during an
  emergency response.
  <div mt="4">
    <span>Topics:</span>
    {#if $tags.length > 2}
      <a chip type="success" href="/" mr="3">all</a>
    {/if}

    {#each $tags as tag}
      <a chip class="" href="/?tag={tag}" mr="3">{tag}</a>
    {/each}
  </div>

</div>
