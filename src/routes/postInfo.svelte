<script>
  export let post;
  const date = post.data.date ? new Date(post.data.date) : null;
  const tags = post.data.tags ? post.data.tags : null;
  let shortDate = isValidDate(date) ? date.toLocaleDateString() : "";
  function isValidDate(d) {
    return d instanceof Date && !isNaN(d);
  }
</script>

<div class="">
  {#each tags as tag}
    <span class="">{tag}</span>
  {/each}

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
  <hr class="" />
</div>
