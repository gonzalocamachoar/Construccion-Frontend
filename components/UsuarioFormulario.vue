<template>
  <div class="userForm">
    <fieldset>
      <legend>Formulario Usuario</legend>

      <form action=""><!--@submit.prevent="guardar"-->
        <label for="ID">ID Usuario</label><br />
        <input
          type="number"
          name="ID"
          id="ID"
          placeholder="ID del Usuario..."
          v-model="usuario.idUsuario"/><br /><br />
        <label for="nombreU">Nombre del Usuario</label><br />
        <input
          type="text"
          name="nombreU"
          id="nombreU"
          placeholder="Nombre del Usuario..."
          v-model="usuario.nombreU"/><br /><br />
        <label for="apellidoU">Apellido del Usuario</label><br />
        <input
          type="text"
          name="apellidoU"
          id="apellidoU"
          placeholder="Apellido del Usuario..."
          v-model="usuario.apellidoU"/><br /><br />
        <label for="tdU">Tipo Docuemento del Usuario</label><br />
        <input
          type="text"
          name="tdU"
          id="tdU"
          placeholder="Tipo Docuemento del Usuario..."
          v-model="usuario.idTipoDoc"/><br /><br />
        <label for="doucmentoU">Documento del Usuario</label><br />
        <input
          type="number"
          name="doucmentoU"
          id="doucmentoU"
          placeholder="Documento del Usuario..."
          v-model="usuario.documentoU"/><br /><br />
        <label for="telefonoU">Telefono del Usuario</label><br />
        <input
          type="text"
          name="telefonoU"
          id="telefonoU"
          placeholder="Telefono del Usuario..."
          v-model="usuario.telefonoU"/><br /><br />
        <label for="direccionU">Direccion del Usuario</label><br />
        <input
          type="text"
          name="direccionU"
          id="direccionU"
          placeholder="Direccion del Usuario..."
          v-model="usuario.direccionU"/><br /><br />
        <label for="emailU">Email del Usuario</label><br />
        <input
          type="text"
          name="emailU"
          id="emailU"
          placeholder="Email del Usuario..."
          v-model="usuario.emailU"/><br /><br />
        <label for="contraseñaU">Contraseña del Usuario</label><br />
        <input
          type="password"
          name="contraseñaU"
          id="contraseñaU"
          placeholder="Contraseña del Usuario..."
          v-model="usuario.contraseñaU"/><br /><br />
        <label for="tipoU">Tipo de Usuario</label><br />
        <input
          type="text"
          name="tipoU"
          id="tipoU"
          placeholder="Tipo de Usuario..."
          v-model="usuario.idTipoUser"/><br /><br />
        <label for="estadoU">Estado del Usuario</label><br />
        <input
          type="text"
          name="estadoU"
          id="estadoU"
          placeholder="Estado del Usuario..."
          v-model="usuario.estadoU"/><br /><br />
        <button type="submit" v-on:click="guardar()">Guardar</button><!--v-on:click="guardar()"-->
        <button type="submit" v-on:click="deleteU(usuario.idUsuario)">Eliminar</button>
      </form>
    </fieldset>
  </div>
</template>
<style>
.userForm {
  text-align: center;
}
</style>
<script>
import axios from "axios";

export default {
  name: "formUser",
  data: function () {
    return {
      usuario: {
        idUsuario: "",
        nombreU: "",
        apellidoU: "",
        idTipoDoc: "",
        documentoU: "",
        telefonoU: "",
        direccionU: "",
        emailU: "",
        contraseñaU: "",
        idTipoUser: "",
        estadoU: "",
      },
    };
  },
  methods:{

    guardar(){

        axios.post('http://localhost:8081/api/user',this.usuario)
        .then(data=>{
            console.log(data);
        })
        
    },deleteU(id){

        axios.delete('http://localhost:8081/api/user/'+id)
        .then(data=>{
            console.log(data)
        })

    }

  }
};
</script>