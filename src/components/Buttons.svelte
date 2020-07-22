<script>
  import { loves } from "../store/store.js";

  function ClickLove() {
    loves.update(n => n + 1);
  }

  function NotLove() {
    loves.update(n => n - 1);
  }
</script>

<style>
  .Buttons {
    width: 30vw;
    margin: 10px auto;
    text-align: center;
    font-size: 90px;
    display: flex;
    justify-content: space-around;
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
  <i class="far fa-times-circle" on:click={NotLove} />
  <i class="far fa-check-circle" on:click={ClickLove} />
</div>
