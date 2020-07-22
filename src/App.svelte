<script>
  import Card from "./components/Card.svelte";
  import { onMount } from "svelte";
  import { loves } from "./store/store.js";
</script>

<style>
  :global(body) {
    padding: 0;
    margin: 0;
  }

  :global(main) {
    font-family: "Anton", sans-serif;
    width: 100vw;
    height: 100vh;
    background-image: linear-gradient(
      to bottom left,
      #ef8042,
      #eb5670,
      #de5887
    );
  }

  div.App {
    width: 100vw;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
  }

  .App .Title {
    color: #ffffff;
    text-align: left;
    font-size: 50px;
    margin: 0px auto 0px 10px;
    border-left: 10px solid white;
    padding-left: 10px;
  }

  .App .Loves {
    color: #ffffff;
    justify-content: flex-start;
    font-size: 50px;
    margin: 0px 10px 0px auto;
    border-right: 10px solid white;
    padding-right: 10px;
  }
</style>

<div>
  <div class="App">
    <h1 class="Title">
      iMatch
      <i class="fas fa-american-sign-language-interpreting" />
    </h1>
    <h3 class="Loves">
      {#if $loves === 0}
        <i class="fas fa-heart-broken" />
      {:else}
        <i class="fas fa-heart" />
      {/if}
      {$loves}
    </h3>
  </div>
  <Card />
</div>
