<script lang="ts"></script>

<svelte:head>
  <title>Om oss - FAD</title>
  <meta name="description" content="Information om FAD och dess styrelse." />
</svelte:head>

{#snippet medlem(name: string, role: string, image: string, position: string = "center")}
  <div class="flex flex-col items-center">
    <img
      src={image}
      alt={name}
      class="h-36 w-36 rounded-full border-3 border-white object-cover shadow-xl transition-transform duration-300"
      style="object-position: {position}; "
    />
    <h2 class="mt-0 text-lg font-semibold">{name}</h2>
    <p class="text-sm text-gray-500">{role}</p>
  </div>
{/snippet}

<main style="min-height: 80vh;">
  <section class="prose prose-base mx-auto mt-20 px-2">
    <h1 class="text-center">FADs styrelse</h1>
    <div class="grid grid-cols-2">
      {@render medlem("Karin Trakell", "Ordförande", "/assets/about/Karin.jpg", "center 20%")}
      {@render medlem("William Minidis", "Kassör", "/assets/about/Minidis.jpg", "center 10%")}
      {@render medlem("Alma Ranefall", "Styrelseledamot", "/assets/about/Alma.png", "center 30%")}
    </div>
  </section>
</main>
