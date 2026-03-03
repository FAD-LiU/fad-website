<script lang="ts">
  import { CONTACT_EMAIL } from "$lib/constants";
  import Link from "$lib/components/Link.svelte";
  import Image from "$lib/components/Image.svelte";
  import Copyright from "$lib/components/Copyright.svelte";
  const contactInfo = `FAD
Kårallen, Universitetet
581 83 Linköping
Sverige`;
</script>

<footer class="bg-fad-black text-fad-white mt-16 text-sm font-light">
  <div
    class="mx-auto grid max-w-[320px] grid-cols-1 gap-y-12 px-4 pt-10 md:max-w-[1000px] md:grid-cols-4"
  >
    <!-- Contact -->
    <div class="md:col-span-2">
      <h2 class="mb-4 text-lg font-bold">Kontakt</h2>
      <pre class="mb-4">{contactInfo}</pre>
      <p>Email: <a href="mailto:{CONTACT_EMAIL}">{CONTACT_EMAIL}</a></p>
    </div>

    <!-- Socials -->
    <div>
      <h2 class="mb-4 text-lg font-bold">Följ oss</h2>
      <ul>
        <li>
          <Link href="https://instagram.com/fad_liu/">Instagram</Link>
        </li>
        <li>
          <Link href="https://facebook.com/profile.php?id=61588212056654">Facebook</Link>
        </li>
        <!-- <li><a href="404.html">LinkedIn</a> &lpar;WIP&rpar;</li> -->
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
  <div class="mx-auto max-w-50 pt-12">
    <p class="text-fad-white/80 text-center">Vi samarbetar med</p>
    <Link href="https://lintek.liu.se/"
      ><Image class="pt-4" src="/assets/lintek.png" alt="LinTek Logotyp" /></Link
    >
  </div>
  <div class="copyright text-fad-white/90 pt-12 pb-4 text-center">
    <Copyright />
  </div>
</footer>
