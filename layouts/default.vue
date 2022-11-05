<template>
  <div>
    <div class="containerDefault">
      <div>
        <ul class="horizontal">
          <li>
            <img
              class="remove-bg"
              href="index.vue"
              src="~/assets/logo.png"
              alt="logo de la epresa"
              width="100px"
            />
          </li>
          <li><a @click="$router.push('/')">Ir a Inicio</a></li>
          <li><a @click="$router.push('/about')"> Quiénes Somos</a></li>
          <li><a @click="$router.push('/productos')"> Nuestros Productos</a></li>
          <li><a @click="$router.push('/pedidos')"> Ordene su pedido</a></li>
          <li><a @click="$router.push('/recetas')"> Nuestras Recetas</a></li>
          <li><a @click="$router.push('/usuario')"> Usuario</a></li>
        </ul>
      </div>
      <div>
        <Nuxt></Nuxt>
      </div>
      <footer>
        <div>
          <p>pie de pagina</p>
        </div>
      </footer>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style>
</style>