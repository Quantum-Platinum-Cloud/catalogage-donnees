<script lang="ts">
  import { onMount } from "svelte";
  import { page } from "$app/stores";
  import { SITE_DESCRIPTION, SITE_TITLE } from "src/constants";

  // CSS
  import "../app.css";
  import "../styles/dsfr-icon-extras.css";

  // DSFR Assets
  import appleTouchFavicon from "@gouvfr/dsfr/dist/favicon/apple-touch-icon.png";
  import svgFavicon from "@gouvfr/dsfr/dist/favicon/favicon.svg";
  import icoFavicon from "@gouvfr/dsfr/dist/favicon/favicon.ico";
  import manifest from "@gouvfr/dsfr/dist/favicon/manifest.webmanifest";

  onMount(async () => {
    // Load the DSFR asynchronously, and only on the browser (not in SSR).
    await import("@gouvfr/dsfr/dist/dsfr/dsfr.module.min.js");
  });

  $: title = $page.data.title || "catalogue.data.gouv.fr";
</script>

<svelte:head>
  <link rel="apple-touch-icon" href={appleTouchFavicon} />
  <!-- 180×180 -->
  <link rel="icon" href={svgFavicon} type="image/svg+xml" />
  <link rel="shortcut icon" href={icoFavicon} type="image/x-icon" />
  <!-- 32×32 -->
  <link rel="manifest" href={manifest} crossorigin="use-credentials" />

  <title>{title}</title>

  <!-- Meta tags for Open Graph -->
  <meta property="og:type" content="website" />
  <meta property="og:title" content={title} />
  <meta name="description" content={SITE_DESCRIPTION} />
  <meta property="og:description" content={SITE_DESCRIPTION} />
  <meta property="og:image:alt" content="République Française - {SITE_TITLE}" />
  <meta property="og:url" content={$page.url.toString()} />

  <!-- Meta tags for Twitter -->
  <meta name="twitter:card" content="summary" />
</svelte:head>

<slot />
