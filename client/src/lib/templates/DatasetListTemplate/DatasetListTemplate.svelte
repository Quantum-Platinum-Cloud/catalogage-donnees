<script lang="ts">
  import { goto } from "$app/navigation";
  import type { Dataset } from "src/definitions/datasets";
  import type { Paginated } from "src/definitions/pagination";
  import { toQueryString } from "$lib/util/urls";
  import { Maybe } from "$lib/util/maybe";
  import DatasetList from "$lib/components/DatasetList/DatasetList.svelte";
  import SearchForm from "$lib/components/SearchForm/SearchForm.svelte";
  import PaginationContainer from "$lib/components/PaginationContainer/PaginationContainer.svelte";
  import paths from "$lib/paths";

  export let paginatedDatasets: Maybe<Paginated<Dataset>>;
  export let currentPage: number;

  const submitSearch = (event: CustomEvent<string>) => {
    const q = event.detail;
    const queryString = toQueryString([["q", q]]);
    const href = `${paths.datasetSearch}${queryString}`;
    goto(href);
  };
</script>

<section class="fr-background-alt--grey fr-mb-6w">
  <div class="fr-container fr-grid-row fr-grid-row--center fr-py-6w">
    <div class="fr-col-10">
      <h1>Recherchez un jeu de données</h1>
      <SearchForm on:submit={submitSearch} />
    </div>
  </div>
</section>

<section class="fr-container">
  <div class="fr-grid-row">
    <div class="fr-col-12">
      {#if Maybe.Some(paginatedDatasets)}
        <h2 class="fr-mb-3w">
          {paginatedDatasets.totalItems} jeux de données contribués
        </h2>

        <DatasetList datasets={paginatedDatasets.items} />

        <PaginationContainer
          {currentPage}
          totalPages={paginatedDatasets.totalPages}
        />
      {/if}
    </div>
  </div>
</section>
