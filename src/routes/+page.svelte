<script lang="ts">
  import BeardGlasses from "$lib/icons/BeardGlasses.svelte";

  // Control margin between "sections".
  // The reason for this bby is that the mission section doesn't
  // actually have a <section> element as its root. Aaaaaand throwing
  // another flex/grid is just overkill.
  const mt = "mt-24";

  // We should probably make some global prose styles.
  // For now, this garbage will do. This essentially unsets
  // a bunch of list styles so that we can keep semantic HTML
  // but style it more freely.
  const proseStyles =
    "prose prose-sm prose-ul:list-none prose-ul:p-0 prose-li:px-4 prose-h2:mt-6 prose-h2:mb-4 prose-li:m-0 prose-h2:text-md prose-h2:font-normal sm:prose-base";
</script>

<svelte:head>
  <title>FAD</title>
  <meta name="description" content="Övergripande information om vad gör FAD" />
</svelte:head>

{#snippet whatWeDoItem(name: String, text: String)}
  <li class="bg-fad-white-pop rounded-lg">
    <h2>{name}</h2>
    <p>{text}</p>
  </li>
{/snippet}

<main class="overflow-y-scroll">
  <!-- Hero -->
  <div
    class="hero border-fad-black h-[60vh] border-b-1 bg-[url(/assets/staben.jpg)] bg-cover bg-center"
  >
    <div
      class="prose prose-invert prose:text-fad-white flex h-full w-full max-w-full flex-col items-center justify-center text-center backdrop-blur-[4px] backdrop-brightness-[0.8]"
    >
      <h1 class="mb-0 text-6xl">
        <span>F</span><span>A</span><span>D</span>
      </h1>
      <p class="mt-2">För en bättre mottagning</p>
    </div>
  </div>

  <div class="mx-auto max-w-5xl px-2">
    <!-- Mission -->
    <div
      class={`glasses-border mx-auto grid grid-cols-1 sm:px-20 lg:grid-cols-[repeat(auto-fill,minmax(400px,1fr))] ${mt}`}
    >
      <section class="prose prose-sm sm:prose-base px-2 lg:py-12">
        <h1>För Fadderister, av fadderister</h1>
        <p>
          FAD är sammarbetsorganisationen för fadderister vid Linköpings universitet. Vi arbetar för
          att göra mottagningen enklare och roligare! Genom att tillhandahålla verktyg, utbildning
          och stöd för mottagningsarrangörer, vill vi göra det lättare att vara fadderist.
        </p>
        <p>
          Vårt mål? En mottagning där både fadderister och nya studenter får den bästa möjliga
          upplevelsen.
        </p>
      </section>
      <div class="flex items-center justify-center">
        <BeardGlasses class="text-fad-black max-h-[250px] sm:max-h-[350px]" />
      </div>
    </div>

    <!-- Services -->
    <section class={`max-w-none ${proseStyles} ${mt}`}>
      <h1>Vad vi gör</h1>
      <ul class="grid grid-cols-1 gap-4 md:grid-cols-3">
        {@render whatWeDoItem(
          "Fadderjobbsportal",
          "Vi erbjuder en platform för fadderier att hantera fadderjobbare och arbetspass under Nolle-P.",
        )}
        {@render whatWeDoItem(
          "Fadderportal",
          "Vi utvecklar en platform för att underlätta informationsspridning mellan fadderister och faddrar.",
        )}
        {@render whatWeDoItem(
          "Kunskapsbank",
          "Vi bygger ut en kunskapsbank för att undvika att generationskunskap går förlorad.",
        )}
      </ul>
    </section>

    <!-- Vision -->
    <section class={`prose prose-sm md:prose-base ${mt}`}>
      <h1>Vår vision</h1>
      <p>
        Vi strävar efter att skapa en bättre mottagning för alla fadderier och fadderister. Genom
        att erbjuda verktyg, resurser och stöd vill vi göra det både enklare och roligare att vara
        fadderist!
      </p>

      <p>
        Har du frågor eller vill du veta mer om oss? Tveka inte att <a
          href="mailto:info@fadderportalen.se">kontakta oss</a
        >!
      </p>
    </section>
  </div>
</main>
