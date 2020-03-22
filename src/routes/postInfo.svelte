<script>
  export let post;
  const date = post.data.date ? new Date(post.data.date) : null;
  const tags = post.data.tags ? post.data.tags : null;
  let shortDate = isValidDate(date) ? date.toLocaleDateString() : "";
  function isValidDate(d) {
    return d instanceof Date && !isNaN(d);
  }
</script>

<div>

  {#each tags as tag}
    <a mr="4" href="/?tag={tag}" class="">{tag}</a>
  {/each}
</div>
<!-- <div>
  {#if post.data.author && post.data.author.name}
    <span class="">{post.data.author.name}</span>
  {/if}

  {#if post.data.author && post.data.author.links}
    {#each post.data.author.links as link}
      <a href={link.url} target="__blank" class="">
        <span>{link.icon}</span>
      </a>
    {/each}
  {/if}

  <span class="">{shortDate}</span>
</div> -->
