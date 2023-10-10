<template>
  <main class="main-height">    
    <router-view/>
  </main>
  <footer class="footer-height">
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
  height: 100vh;
  overflow: hidden;
}

.center-container {
  text-align: center;
}

.main-height {
  height: 95%;
  margin: 0;
  padding: 0;
}

.footer-height {
  height: 5%;
}
</style>
