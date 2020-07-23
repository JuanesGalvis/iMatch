<script>
  import { loves } from "./store/store.js";
  import { Nop } from "./store/store.js";
  import Card from "./components/Card.svelte";
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
    font-size: 50px;
    margin: 0px 10px 0px auto;
    border-right: 10px solid white;
    padding-right: 10px;
  }

  .Contadores {
    display: flex;
  }
</style>

<div>
  <div class="App">
    <h1 class="Title">
      iMatch
      <i class="fas fa-american-sign-language-interpreting" />
    </h1>
    <div class="Contadores">
      <h3 class="Loves">
        <i
          class="fas fa-heart-broken"
          aria-label="Personal que no te gustaron" />
        {$Nop}
        <i class="fas fa-heart" aria-label="Personal que te gustaron" />
        {$loves}
      </h3>
    </div>
  </div>

  <Card />

</div>
