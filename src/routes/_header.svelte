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

<section p="8 sm3">
  <ul grid columns="3" gap="6">
    <li cell span="3">
      <h1 pb="6">
        <a class={segment === undefined ? '' : ''} color="black" href=".">
          Emergency FYI for XYZ
        </a>
      </h1>
    </li>
    <li cell span="2">
      <h2>
        Help exists if you know where to find it.
      </h2>
      <h3>XYZ is overwhelming the state and federal capacities of the US government. We're centralizing resources to help you navigate this ongoing crisis. Listed are active efforts to mitigate the worst effects of this crisis. We've organized them into a dozen key topics.</h3>
    </li>
    <li cell span="2">
      <h2>Topics:</h2>
      {#each $tags as tag}
        <a class="h3" href="/?tag={tag}" mr="2">{tag}</a>
      {/each}<span></span><a href="/" class="h3" mr="2">clear</a>
    </li>
  </ul>
</section>
