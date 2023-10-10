<template>
    <div class="image-background" :style="backgroundImageStyle">
      <h2>Mon Composant avec Image en Arrière-Plan</h2>
      <p>Ceci est le contenu de mon composant.</p>
    </div>
</template>
  
<script>
export default {
  data() {
    return {
      imageUrl: '../assets/CEO.jpg',
    };
  },
  computed: {
    backgroundImageStyle() {
      return {
        backgroundImage: '../assets/CEO.jpg',
        backgroundSize: 'cover',
        backgroundPosition: 'center center',
      };
    },
  },
};
</script>

<style scoped>
.image-background {
  width: 100%;
  text-align: center;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.image-background h2, .image-background p {
  margin: 0;
}

</style>
  