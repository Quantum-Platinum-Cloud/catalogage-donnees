<script lang="ts">
  import paths from "$lib/paths";
  import { SITE_DESCRIPTION } from "src/constants";
</script>

<!-- svelte-ignore a11y-no-redundant-roles // This is the main app's footer so we keep the role explicit -->
<footer class="fr-footer" role="contentinfo" id="footer">
  <div class="fr-container">
    <div class="fr-footer__body">
      <div class="fr-footer__brand fr-enlarge-link">
        <a href={paths.home} title="Retour à l'accueil">
          <p class="fr-logo">
            République
            <br />Française
          </p>
        </a>
      </div>
      <div class="fr-footer__content">
        <p class="fr-footer__content-desc">
          {SITE_DESCRIPTION}
        </p>
        <ul class="fr-footer__content-list">
          <li class="fr-footer__content-item">
            <a class="fr-footer__content-link" href="https://legifrance.gouv.fr"
              >legifrance.gouv.fr</a
            >
          </li>
          <li class="fr-footer__content-item">
            <a class="fr-footer__content-link" href="https://gouvernement.fr"
              >gouvernement.fr</a
            >
          </li>
          <li class="fr-footer__content-item">
            <a class="fr-footer__content-link" href="https://service-public.fr"
              >service-public.fr</a
            >
          </li>
          <li class="fr-footer__content-item">
            <a class="fr-footer__content-link" href="https://data.gouv.fr"
              >data.gouv.fr</a
            >
          </li>
        </ul>
      </div>
    </div>
    <div class="fr-footer__bottom">
      <ul class="fr-footer__bottom-list">
        <li class="fr-footer__bottom-item">
          <a
            href={paths.declarationAccessibilite}
            class="fr-footer__bottom-link"
          >
            Accessibilité: non conforme
          </a>
        </li>
        <li class="fr-footer__bottom-item">
          <a class="fr-footer__bottom-link" href={paths.mentionsLegales}>
            Mentions légales
          </a>
        </li>
        <li class="fr-footer__bottom-item">
          <a class="fr-footer__bottom-link" href={paths.viePrivee}>
            Vie privée
          </a>
        </li>
      </ul>
      <div class="fr-footer__bottom-copy">
        <p>
          Sauf mention contraire, tous les contenus de ce site sont sous <a
            href="https://github.com/etalab/licence-ouverte/blob/master/LO.md"
            target="_blank">licence etalab-2.0</a
          >
        </p>
      </div>
    </div>
  </div>
</footer>
