<script lang="ts">
  import { page } from "$app/stores";

  let scrollY = $state(0);

  // Solid header unless the landing page
  let isScrolled = $derived(scrollY > 0 || $page.url.pathname !== "/");
</script>

<!-- Bin scroll state to window scroll -->
<svelte:window bind:scrollY />

{#snippet navLink(href: string, text: String)}
  <li class="min-w-fit text-center text-sm">
    <a class="no-underline hover:underline" {href}>{text}</a>
  </li>
{/snippet}

<nav
  class="text-fad-white text-md z-50 w-full transition-all duration-500 ease-in-out"
  class:navbar-default={!isScrolled}
  class:navbar-scrolled={isScrolled}
>
  <div class="mx-auto flex h-full w-full max-w-[128rem] flex-row justify-between px-2 lg:px-20">
    <!-- Logo -->
    <div class="my-auto hidden md:block">FAD Logga &lpar;WIP&rpar;</div>

    <!-- Nav links -->
    <div
      class="bg-fad-black/75 mx-auto flex flex-row items-center gap-x-4 rounded-lg px-8 md:mx-0"
      class:outline-2={!isScrolled}
      class:outline-fad-white={!isScrolled}
    >
      <ul class="flex flex-row gap-x-4">
        {@render navLink("/", "Hem")}
        {@render navLink("/about", "Om oss")}
      </ul>
      <div
        class="divider-horizontal"
        style="height: 1rem; width: 2px; background-color: var(--color-fad-white);"
      ></div>
      <a
        class="bg-fad-green rounded-sm px-4 py-[1px] text-black no-underline"
        href="mailto:info@fadderportalen.se">Kontakt</a
      >
    </div>
  </div>
</nav>
