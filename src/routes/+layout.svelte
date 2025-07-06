<script lang="ts">
  import "../app.css";

  import Navbar from "$lib/layout/Navbar.svelte";
  import Footer from "$lib/layout/Footer.svelte";

  // Add prerendering for root layout
  export const prerender = true;

  let { children } = $props();
</script>

<Navbar />
{@render children()}
<Footer />
