<template>
    <div>
        <img alt="Vue logo" src="../assets/logo.png">
        <h2>Tabla de registros</h2>
         <div class="col-md-12">
             <tabla-personas :personas="personas"
             @delete-persona="eliminarPersona"
             @actualizar-persona="actualizarPersona"/>
        </div>
    </div>
</template>
<script>

import TablaPersonas from '../components/TablaPersonas.vue'

  export default {
    name: 'app',
    components: {
        TablaPersonas
    },
    methods: {
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