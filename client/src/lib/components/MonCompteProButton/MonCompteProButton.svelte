<script lang="ts">
  import franceConnect from "$lib/assets/france-connect.svg";
</script>

<div>
  <button class="fr-mb-1w" aria-label="s'identifier avec MonComptePro" on:click>
    <img class="padlock" alt="" src={franceConnect} />

    <p class="fr-pl-1w">
      S'identifier avec <br />
      <span class="fr-text--bold">MonComptePro</span>
    </p>
  </button>

  <a
    class="fr-link fr-link--sm"
    href="http://mon-compte-pro.beta.gouv.fr/"
    target="_blank"
  >
    Qu'est-ce que MonComptePro ?</a
  >
</div>

<style>
  button {
    background-color: #006adc;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 4px 8px;
  }

  button:hover {
    background-color: #3e89da;
  }

  p {
    margin: 0;
    padding: 0;
    color: white;
    line-height: 1 !important;
  }
</style>
