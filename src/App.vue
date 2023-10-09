<template>
    <img alt="menu de l'escape game" class="test" src="./assets/menu.jpg" />
  <v-icon size="large" color="green-darken-2" icon="mdi-information" />
  <main>    
    <router-view/>
  </main>
  <footer>
    <AppFooter></AppFooter>
  </footer>
</template>

<script>
import AppFooter from '@/components/AppFooter.vue';

export default {
  name: "App",
  components: {
    AppFooter
  }
};
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
