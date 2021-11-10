<template>
<div id="nav">
    <!-- Usa el componente router-link la navegación. -->
    <!-- Especifica la ruta usando la propiedad `to`. -->
    <!-- `<router-link>` será renderizado como una etiqueta `<a>` por defecto -->
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div>
 <router-view></router-view>
   <Movies />
</template>

<script>
import Movies from './components/Movies.vue'
export default {
  name: 'App',
  components: {
      Movies,
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
