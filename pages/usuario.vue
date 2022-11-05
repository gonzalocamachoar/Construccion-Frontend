<template>
    <div class="containerUser">
       <UsuarioFormulario/>
        <UsuarioTabla/>
    </div>
</template>
<script>

import formUser from '@/components/UsuarioFormulario.vue'
import tableUser from '@/components/UsuarioTabla.vue'

export default{
    name: 'usuario',
    layout: 'default',
    components: {

        formUser,tableUser
        
    }

}


</script>