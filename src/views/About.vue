<template>
  <div class="about">
    <h1>This is an about page whit a form</h1>
    <br>
    <div class="col-md-12">
      <formulario-persona @add-persona="agregarPersona"/>
    </div>
  </div>
</template>

<script>
  import FormularioPersona from '../components/FormularioPersona.vue'
  export default {
    name: 'app',
    components: {
      FormularioPersona,
    },
  }
</script>

<style>

  button {
    background: #009435;
    border: 1px solid #009435;
  }

  header{
    background-color: rgb(66, 252, 9);
    border-radius: 15px;
    color: black;
    background-image: var(--bs-gradient);
  }

  .bg-secondary {
  background-color: rgba(var(--bs-secondary-rgb), var(--bs-bg-opacity)) !important;
  background-image: var(--bs-gradient);
  }
</style>
