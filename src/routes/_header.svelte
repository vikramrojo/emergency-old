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
          Emergency FYI for COVID-19
        </a>
      </h1>
    </li>
    <li cell span="2">
      <h2>
        Help exists if you know where to find it.
      </h2>
      <h3>COVID-19 is overwhelming state and federal capacities of the US government. This site is designed to centralize the resources, helping you navigate this ongoing crisis. Listed below are active efforts to mitigate the worst effects, organized into key topic area.</h3>
    </li>
    <li cell span="2">
      <h2>Topics:</h2>
      {#each $tags as tag}
        <a class="h3" href="/?tag={tag}" mr="2">{tag}</a>
      {/each}<span></span><a href="/" class="h3" mr="2">clear</a>
    </li>
  </ul>
</section>
