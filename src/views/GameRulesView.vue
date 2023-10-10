<template>
  <header>
    <AppNavigation/>
  </header>
  <div class="container-fluid">
    <h1 class="text-center">Règles du Jeu - Escape Game contre le Harcèlement au Travail</h1>
    <div class="scrollable-content">
    <h2 class="text-center">Objectif du Jeu</h2>
    <p>L'objectif de cet escape game est de sensibiliser les participants aux problèmes de harcèlement au travail et de promouvoir un environnement de travail respectueux et inclusif.</p>

    <h2  class="text-center" >Règles Générales</h2>
    <ul>
      <li>Le jeu se déroule dans une série de pièces virtuelles.</li>
      <li>Les participants doivent résoudre des énigmes et des défis pour progresser d'une pièce à l'autre.</li>
      <li>Le jeu a un temps limité, et les participants doivent travailler ensemble pour terminer le jeu dans le délai imparti.</li>
      <li>Les participants doivent faire preuve d'empathie, de respect et de communication efficace pour réussir.</li>
    </ul>

    <h2  class="text-center">Thème du Harcèlement au Travail</h2>
    <p>Chaque pièce du jeu est conçue pour mettre en évidence différents aspects du harcèlement au travail, tels que le harcèlement sexuel, le harcèlement moral, et le harcèlement basé sur la race, le genre, ou d'autres caractéristiques.</p>

    <h2  class="text-center">Conseils pour les Participants</h2>
    <p>Voici quelques conseils pour les participants :</p>
    <ul>
      <li>Écoutez activement les autres participants et partagez vos idées.</li>
      <li>Soyez respectueux envers les opinions et les expériences des autres.</li>
      <li>Si vous êtes témoin de harcèlement, signalez-le immédiatement et demandez de l'aide.</li>
      <li>Utilisez la communication non violente pour résoudre les conflits.</li>
      <li>Rappelez-vous que le harcèlement au travail est inacceptable et peut avoir des conséquences graves.</li>
    </ul>

    <h2  class="text-center">Fin du Jeu</h2>
    <p>Une fois que les participants ont terminé toutes les pièces et ont résolu les défis liés au harcèlement au travail, le jeu se termine avec un message sur l'importance de la prévention du harcèlement au travail et de la création d'un environnement de travail sûr et inclusif pour tous.</p>
  </div>
  </div>
  <BackToHomeButton />
</template>

<script>
import AppNavigation from '@/components/AppNavigation.vue';

export default {
  name: 'GameRulesView',
  components: {
    AppNavigation,
  }
}
</script>
<style>
.scrollable-content {
  max-height: 70vh;
  overflow-y: auto;
}
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
</style>
