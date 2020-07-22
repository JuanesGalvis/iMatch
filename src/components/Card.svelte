<script>
  import Buttons from "./Buttons.svelte";
</script>

<style>
  .Datos {
    margin: 40px auto;
    width: 50vw;
    height: 100%;
    text-align: center;
    color: white;
    display: flex;
    justify-content: center;
    align-self: center;
  }

  .Datos img {
    width: 300px;
    height: 300px;
    border-radius: 100%;
    box-shadow: 0px 7px 80px black;
  }

  .Datos .info h2 {
    font-size: 40px;
    border-bottom: 3px solid white;
    padding-bottom: 5px;
    margin-top: 20px;
  }

  .Datos p {
    font-size: 18px;
  }

  .Datos .info i.fa-venus {
    font-size: 60px;
  }
</style>

<div class="Datos">
  <figure>
    <img
      src="https://bolavip.com/__export/1588979208273/sites/bolavip/img/2020/05/08/greeicy-rendoxn-1280x720_jpg_1889316708_crop1588979207804.jpg_1902800913.jpg"
      alt="Person" />
  </figure>
  <div class="info">
    <i class="fas fa-venus" />
    <h2>Una Woman</h2>
    <p>Medellín ~ Colombia</p>
    <p>Desarrolladora Web</p>
    <p>444 44 44</p>
  </div>
</div>
<Buttons />
