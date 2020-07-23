<script>
  import Buttons from "./Buttons.svelte";
  import { onMount } from "svelte";

  let Tec = [
    "Frontend",
    "Backend",
    "Data Science",
    "Scrum Master",
    "Founder",
    "Python Dev",
    "Graphic designer",
    "Community Manager",
    "Mobile apps",
    "cybersecurity",
    "Audiovisual Product"
  ];
  let datos = {};
  let datosEnv = {};
  onMount(CallFetch);

  async function CallFetch() {
    const res = await fetch("https://randomuser.me/api/");
    datos = await res.json();
    await console.log(datos);
    await RenderCard(datos);
  }

  function RenderCard(data) {
    let Trabajo = Tec[parseInt(Math.random() * 11)];

    datosEnv = {
      Nombre: data.results[0].name.first,
      Apellido: data.results[0].name.last,
      Ciudad: data.results[0].location.city,
      Pais: data.results[0].location.state,
      Celular: data.results[0].phone,
      Genero: data.results[0].gender,
      Jobs: Trabajo,
      Foto: data.results[0].picture.large,
      Correo: data.results[0].email
    };
  }
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

  .Datos .info .Left {
    text-align: left;
  }

  p.Contact {
    display: flex;
    justify-content: space-around;
    font-size: 28px;
  }

  p.Contact a {
    text-decoration: none;
    color: white;
  }
</style>

<div class="Datos">
  <figure>
    <img src={datosEnv.Foto} alt={datosEnv.Nombre} />
  </figure>
  <div class="info">
    <div class="Left">
      <h2 aria-label={datosEnv.Nombre}>
        {datosEnv.Nombre} {datosEnv.Apellido}
      </h2>
      <h3 aria-label={datosEnv.Correo}>
        <i class="far fa-envelope-open" />
        {datosEnv.Correo}
      </h3>
      <p aria-label={datosEnv.Ciudad}>
        <i class="fas fa-city" />
        {datosEnv.Ciudad} ~ {datosEnv.Pais}
      </p>
      <p aria-label={datosEnv.Jobs}>
        <i class="fas fa-briefcase" />
        {datosEnv.Jobs}
      </p>
      <p aria-label={datosEnv.Celular}>
        <i class="fab fa-whatsapp" />
        {datosEnv.Celular}
      </p>
      <p
        class="Contact"
        aria-label="Cuenta con perfil en GitHub, Twitter y Linkedin">
        <a href="#">
          <i class="fab fa-github" />
        </a>
        <a href="#">
          <i class="fab fa-twitter" />
        </a>
        <a href="#">
          <i class="fab fa-linkedin-in" />
        </a>
      </p>
    </div>
  </div>
</div>
<Buttons on:click={CallFetch} on:keypress={CallFetch} />
