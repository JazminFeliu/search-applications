<script>
  let value = "";
  let louding = false;
  let response = [];

  const handleInput = (event) => (value = event.target.value);

  $: if (value.length > 2) {
    loading = true;

    fetch(`http://www.omdbapi.com/?s=${value}&apikey=422350ff`)
      .then((res) => res.json())
      .then((apiResponse) => {
        response = apiResponse.Search || [];

        louding = false;
      });
  }
</script>

<input placeholder="Search movies..." {value} on:input={handleInput} />

{#if loading}
  <strong>Loading...</strong>
{:else if response.length > 0}
  <strong>Tenemos {response.length} películas</strong>
{:else}
  <strong>No hay resultados</strong>
{/if}
