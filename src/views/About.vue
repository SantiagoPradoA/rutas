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