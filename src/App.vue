<template>
  <div id="app">
    <div class="center-container">
      <div class="image-container">
        <img alt="menu de l'escape game" src="./assets/menu.jpg" />
      </div>
    </div>
    <v-icon size="large" color="green-darken-2" icon="mdi-information" />
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
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
