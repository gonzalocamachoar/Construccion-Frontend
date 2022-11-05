<template>
    <div class="userTable">
        <fieldset>
            <legend>Tabla de Usuarios</legend>
            <label for="idUser">ID Usuario</label>
            <form @submit.prevent="burcarPorID"><input v-model="id" type="number"><button type="submit">Buscar Usuario</button></form>

            <table>
                <tr>
                    <th>ID Usuario</th>
                    <th>Nombre</th>
                    <th>Apellido</th>
                    <th>Tipo Doc</th>
                    <th>Documento</th>
                    <th>Telefono</th>
                    <th>Direccion</th>
                    <th>Email</th>
                    <th>Contraseña</th>
                    <th>Tipo User</th>
                    <th>Estado</th>
                </tr>
                <tr v-for="usuario in usuarios" :key="usuario.idUsuario">
                    <td>{{usuario.idUsuario}}</td>
                    <td>{{usuario.nombreU}}</td>
                    <td>{{usuario.apellidoU}}</td>
                    <td>{{usuario.idTipoDoc}}</td>
                    <td>{{usuario.documentoU}}</td>
                    <td>{{usuario.telefonoU}}</td>
                    <td>{{usuario.direccionU}}</td>
                    <td>{{usuario.emailU}}</td>
                    <td>{{usuario.contraseñaU}}</td>
                    <td>{{usuario.idTipoUser}}</td>
                    <td>{{usuario.estadoU}}</td>
                </tr>
            </table>

        </fieldset>
    </div>


</template>
<script>
import axios from 'axios'
export default{

    name:'userTable',
    data(){
        return{
            usuarios: [],
            id: null
        }
    },mounted(){

        let vue=this;

        axios.get('http://localhost:8081/api/user/listar')
        .then(response=>{
            vue.usuarios=response.data;
        })

    },methods: {
        async burcarPorID(){

            const resp = await this.$axios.get(`http://localhost:8081/api/user/${this.id}`)
            console.log(this.usuarios)
            this.usuarios=[resp.data]
            console.log(this.usuarios)

        }
    }


}
</script>
<style>
.userTable{
    text-align: center;
}
</style>
