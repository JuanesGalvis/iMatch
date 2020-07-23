<script>
  import { loves } from "../store/store.js";
  import { Nop } from "../store/store.js";

  function ClickLove() {
    loves.update(n => n + 1);
  }

  function NotLove() {
    Nop.update(n => n + 1);
  }
</script>

<style>
  .Buttons {
    width: 30vw;
    margin: 0 auto;
    text-align: center;
    font-size: 90px;
    display: flex;
    justify-content: space-around;
  }

  .Buttons a {
    text-decoration: none;
    margin: 0;
  }

  .Buttons .far {
    border-radius: 100%;
    box-shadow: 0;
    transition: 0.5s box-shadow;
    cursor: pointer;
    background-color: #ed7160;
  }

  .Buttons .fa-times-circle {
    color: white;
  }

  .Buttons .fa-check-circle {
    color: white;
  }

  .Buttons .far:hover {
    border-radius: 100%;
    box-shadow: -10px 9px 13px black;
    transition: 0.5s box-shadow;
  }
</style>

<div class="Buttons">
  <a href="#">
    <i
      class="far fa-times-circle"
      on:click
      on:keypress
      on:click={NotLove}
      on:keypress={NotLove}
      aria-label="No te gusta" />
  </a>
  <a href="#">
    <i
      class="far fa-check-circle"
      on:click
      on:keypress
      on:click={ClickLove}
      on:keypress={ClickLove}
      aria-label="Si te gusta" />
  </a>
</div>
