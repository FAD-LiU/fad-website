<script lang="ts"></script>

<svelte:head>
  <title>Om oss - FAD</title>
  <meta name="description" content="Information om FAD och dess styrelse." />
</svelte:head>

{#snippet medlem(name: string, role: string, image: string)}
  <div class="flex flex-col items-center">
    <img src={image} alt={name} class="h-32 w-32 rounded-full" />
    <h2 class="mt-0 text-lg font-semibold">{name}</h2>
    <p class="text-sm text-gray-500">{role}</p>
  </div>
{/snippet}

<main style="min-height: 80vh;">
  <section class="prose prose-base mx-auto mt-20 px-2">
    <h1 class="text-center">FADs styrelse</h1>
    <div class="grid grid-cols-2">
      {@render medlem("Tobias Elfstrand", "Ordförande", "https://robohash.org/Tobias_Elfstrand")}
      {@render medlem("Fredrik Eriksson", "Kassör", "https://robohash.org/Fredrik_Eriksson")}
      {@render medlem("Emma Lundvall", "Styrelseledamot", "https://robohash.org/Emma_Lundvall")}
      {@render medlem(
        "Andreas Blomqvist",
        "Styrelseledamot",
        "https://robohash.org/Andreas_Blomqvist",
      )}
      {@render medlem(
        "Oskar Arensmeier",
        "Styrelseledamot",
        "https://robohash.org/Oskar_Arensmeier",
      )}
    </div>
  </section>
</main>
