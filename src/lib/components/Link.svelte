<script>
  // 'href' is required, so we don't give it a default value
  export let href;

  $: isExternal = /^[a-z][a-z\d+\-.]*:\/\//i.test(href);
</script>

<a
  {href}
  {...$$restProps}
  target={isExternal ? "_blank" : null}
  rel={isExternal ? "noopener noreferrer" : null}
>
  <slot />
</a>
