<script>
  let value = "";
  let response = [];

  const handlerInput = (event) => (value = event.target.value);

  $: if (value.length > 2) {
    fetch(`http://www.omdbapi.com/?s=${value}&apikey=422350ff`)
      .then((res) => res.json())
      .then((apiResponse) => {
        response = apiResponse.Search;
        console.log(apiResponse);
      });
  }
</script>

<input {value} on:input={handlerInput} />
