<template>
<body class="p-3 mb-2 bg-secondary bg-gradient text-white" style="--bs-bg-opacity: .5;">
  <div id="app" class="container">
    <div class="row">
      <div class="col-md-20">
        <header class="bg-gradient border border-5 col-md-20 dropdown-header">
          <h1>PERSONAS</h1>
        </header>
      </div>
      <div class="row">
        <div class="col-md-12">
          <formulario-persona @add-persona="agregarPersona"/>
          <tabla-personas :personas="personas" 
          @delete-persona="eliminarPersona"
          @actualizar-persona="actualizarPersona"/>
        </div>
      </div>
    </div>
  </div>
</body>
</template>
<script>
  import FormularioPersona from '../components/FormularioPersona.vue'
  import TablaPersonas from '../components/TablaPersonas.vue'

  export default {
    name: 'app',
    components: {
      FormularioPersona,
      TablaPersonas
    },
    methods: {
        agregarPersona(persona){
          let id = 0;
          if (this.personas.length > 0) {
            id = this.personas[this.personas.length - 1].id + 1;
          }
          this.personas= [...this.personas, { ...persona, id}];
        },
        eliminarPersona(id){
            this.personas = this.personas.filter(
              persona => persona.id !== id
            );
        },
        actualizarPersona(id, personaActualizada) {
          this.personas = this.personas.map(persona =>
          persona.id === id ? personaActualizada : persona)
        }
    },
  data() {
    return {
        personas: [
        {
          id: 1,
          nombre: 'Jon',
          apellido: 'Nieve',
          email: 'jon@email.com',
        },
        {
          id: 2,
          nombre: 'Tyrion',
          apellido: 'Lannister',
          email: 'tyrion@email.com',
        },
        {
          id: 3,
          nombre: 'Daenerys',
          apellido: 'Targaryen',
          email: 'daenerys@email.com',
        },
      ],
    }
  }
}
</script>

<style>
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
  #nav {
  padding: 30px;
  }

  #nav a {
    font-weight: bold;
    color: #2c3e50;
  }

  #nav a.router-link-exact-active {
    color: #42b983;
  }

</style>