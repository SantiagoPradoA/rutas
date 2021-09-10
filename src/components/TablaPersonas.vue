<template>
  <div id="tabla-personas">
    <br>
    <div class="alert alert-warning col-md-5" role="alert">
      No se han agregado registros
    </div>
    <table class="table table-dark table-striped table-hover table-borderless">
      <thead>
        <tr>
          <th>Nombre</th>
          <th>Apellido</th>
          <th>Email</th>
          <th>Acciones</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "tabla-personas",
  props: {
    personas: Array,
  },
  data() {
    return {
      editando: null,
    };
  },
  methods: {
    editarPersona(persona) {
      this.personaEditada = Object.assign({}, persona);
      this.editando = persona.id;
    },
    guardarPersona(persona) {
      if (!persona.nombre.length || !persona.apellido.length || !persona.email.length) {
        return;
      }
      this.$emit("actualizar-persona", persona.id, persona);
      this.editando = null;
    },
    cancelarEdicion(persona) {
      Object.assign(persona, this.personaEditada);
      this.editando = null;
    },
  },
};
</script>

<style scoped>
  .btn-outline-danger{
    background-color: red;
    color: antiquewhite;
    background-image: var(--bs-gradient);
  }
  .btn-outline-warning{
    background-color: yellow;
    color: black;
    background-image: var(--bs-gradient);
  }
  .btn-outline-secondary{
    background-color: indigo;
    color: azure;
    background-image: var(--bs-gradient);
  }
  .btn-outline-success{
    background-color: rgb(10, 189, 40);
    color: gainsboro;
    background-image: var(--bs-gradient);
  }
</style>