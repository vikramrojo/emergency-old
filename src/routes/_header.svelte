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

<style>

#topics {
  position:sticky;
  top:0;
}

</style>

<section p="8 sm3" bg="gray3">
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
      <p>The COVID-19 pandemic is overwhelming federal, state, and local capacities of the United States government. We can help you find resources and aid in your local area to navigate this ongoing crisis, and expand your network for volunteer work. Listed below are active efforts to mitigate the worst effects, organized by key topic area.</p>
    </li>
  </ul>
</section>

<div alert type="alert" color="white" class="h3" flex px="8 sm3" align="center" py="4"><span>We have 2 critical weeks to slow the spread of Coronavirus. Start by following the US Government response.</span><a button ml="4" href="https://www.coronavirus.gov/">coronavirus.gov</a></div>

<section p="8 sm3" id="topics" bg="gray1">
  <ul grid columns="3" gap="6">
    <li cell span="3">
      <div>
        <span class="h3" mr="3">Topics:</span>
        <a href="/state-dept" chip type="primary" class="h4" mr="2">State and Local Health Departments</a>
        {#each $tags as tag}
          <a chip type="primary" class="h4" href="/?tag={tag}" mr="4" my="1">{tag}</a>
        {/each}<a href="/" class="h3" mr="2">ALL</a>
      </div>
    </li>
  </ul>
</section>
