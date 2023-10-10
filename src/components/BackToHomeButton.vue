<template>
    <button class="back-to-home-button" @click="navigateToHome">RETOUR AU PLATEAU</button>
  </template>
  
  <script>
  export default {
    methods: {
      navigateToHome() {
        this.$router.push({ name: 'home' }); // Redirige vers la page d'accueil
      },
    },
  };
  </script>
  
  <style scoped>
    .back-to-home-button {
        position: fixed;
        font-weight: bold;
        top: 1%;
        left: 50%;
        transform: translateX(-50%); /* Centre horizontalement le bouton */
        z-index: 999;
        padding: 10px 20px;
        background-color: #0e5e0b  !important;
        color: white !important;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }

    /* Style au survol du bouton (optionnel) */
    .back-to-home-button:hover {
        background-color: #D4AF37 !important;
    }
  </style>
  