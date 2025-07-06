<script lang="ts">
  const contactInfo = `FAD
Kårallen, Universitetet
581 83 Linköping
Sverige`;
</script>

<footer class="bg-fad-black text-fad-white mt-16 text-sm font-light">
  <div
    class="mx-auto flex max-w-[320px] grid-cols-4 flex-col gap-y-6 px-4 pt-10 sm:grid sm:max-w-[1000px] sm:flex-none"
  >
    <!-- Contact -->
    <div>
      <h2 class="mb-4 text-lg font-bold">Kontakt</h2>
      <pre class="mb-4">{contactInfo}</pre>
      <p>Email: <a href="mailto:info@fadportalen.se">info@fadportalen.se</a></p>
    </div>

    <!-- Dummy for col alignment -->
    <div class="hidden md:block"></div>

    <!-- Socials -->
    <div>
      <h2 class="mb-4 text-lg font-bold">Följ oss</h2>
      <ul>
        <li><a href="404.html">Facebook</a> &lpar;WIP&rpar;</li>
        <li><a href="404.html">Instagram</a> &lpar;WIP&rpar;</li>
        <li><a href="404.html">LinkedIn</a> &lpar;WIP&rpar;</li>
      </ul>
    </div>

    <!-- Documents -->
    <div>
      <h2 class="mb-4 text-lg font-bold">Dokument</h2>
      <ul>
        <li><a href="/documents/Stadgar.pdf">Stadgar</a></li>
        <!-- TODO: Skapa datahanteringspolicy -->
        <!-- <li><a href="404.html">Datahanteringspolicy</a></li> -->
      </ul>
    </div>
  </div>
  <div class="copyright text-fad-white/90 pt-12 pb-4 text-center">
    <p>&copy; 2025 FAD</p>
  </div>
</footer>
