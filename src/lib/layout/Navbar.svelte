<script lang="ts">
  import { page } from "$app/state";
  import { CONTACT_EMAIL } from "$lib/constants";
  import Link from "$lib/components/Link.svelte";
  import Image from "$lib/components/Image.svelte";

  let scrollY = $state(0);
  let innerHeight = $state(0); // Tracks the physical height of the browser window

  // The hero is 60vh (60% of window height).
  // Switch the navbar state exactly when we scroll past that pixel value.
  let isScrolled = $derived(scrollY > innerHeight * 0.25 || page.url.pathname !== "/");
</script>

<!-- Bin scroll state to window scroll -->
<svelte:window bind:scrollY bind:innerHeight />

{#snippet navLink(href: string, text: string)}
  <li class="text-md min-w-fit text-center">
    <Link class="no-underline hover:underline" {href}>{text}</Link>
  </li>
{/snippet}

<nav
  class="text-fad-white text-md z-50 w-full transition-all duration-500 ease-in-out"
  class:navbar-default={!isScrolled}
  class:navbar-scrolled={isScrolled}
>
  <div class="mx-auto flex h-full w-full max-w-[128rem] flex-row justify-between px-2 lg:px-20">
    <!-- Logo -->
    <div
      class="flex items-center transition-all duration-500 ease-in-out {!isScrolled
        ? 'h-18 lg:h-32'
        : 'h-full'}"
    >
      <Image src="/favicon.svg" class="h-full w-auto object-contain" />
    </div>

    <!-- Nav links -->
    <div
      class="bg-fad-black/75 mx-auto flex flex-row items-center gap-x-4 rounded-lg px-6 md:mx-0"
      class:outline-2={!isScrolled}
      class:outline-fad-white={!isScrolled}
    >
      <ul class="flex flex-row gap-x-4">
        {@render navLink("/", "Hem")}
        {@render navLink("/about", "Om oss")}
      </ul>
      <div
        class="divider-horizontal"
        style="height: 2rem; width: 2px; background-color: var(--color-fad-white);"
      ></div>
      <Link
        class="bg-fad-green rounded-sm border-transparent px-4 py-[1px] text-black no-underline transition hover:ring-2"
        href="mailto:{CONTACT_EMAIL}">Kontakt</Link
      >
    </div>
  </div>
</nav>
