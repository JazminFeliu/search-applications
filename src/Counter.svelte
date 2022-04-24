<script>
  export let initialCounter = 0;
  let contador = initialCounter;
  export let maxCounter = 9;

  function handleClick() {
    contador++;
  }

  $: isEvenOrOdd = contador % 2 === 0 ? "Is Even" : "Is Odd";
  $: if (contador > maxCounter) {
    console.log("limit contador");
    contador = maxCounter;
  }
</script>

<button on:click={handleClick}>Incrementar</button>
<span> {contador} </span>
<span>{isEvenOrOdd} </span>

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
