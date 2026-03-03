<script>
  // 'href' is required, so we don't give it a default value
  export let src;
</script>

<img {src} {...$$restProps} loading="lazy" />
