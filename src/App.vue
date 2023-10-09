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
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  overflow: hidden;
}

.center-container {
  text-align: center;
}

.image-container {
  max-width: 100%;
  max-height: 100%;
  transform: scale(0.9);
  overflow: hidden;
}

img {
  width: 100%;
  height: 100%;
}
</style>
