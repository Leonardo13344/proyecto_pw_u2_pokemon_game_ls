<template>
<img src="./assets/logo.png" alt="">
  <!--<PokemonPage />-->
  <router-view />
  <ComponentePicture />
</template>

<script>

//import PokemonPage from '@/components/PokemonPage.vue'
//import AboutPage from './modulos/pokemon/pages/AboutPage.vue'
import ComponentePicture from './modulos/pokemon/componentes/ComponentePicture.vue'

export default {
  name: 'App',
  components: {
    ComponentePicture
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
