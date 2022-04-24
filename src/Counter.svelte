<script>
  export let initialCounter = 0;
  let contador = initialCounter;

  function handleClick() {
    contador++;
  }
</script>

<button on:click={handleClick}>Incrementar</button>
<span> {contador} </span>

<style>
  span {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 2em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
