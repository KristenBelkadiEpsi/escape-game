<template>
  <BackToHomeButton />
  <div class="image-background container" :style="backgroundImageStyle">
      <v-btn
          class="clickable-area"
      >

      <v-dialog
          v-model="dialog"
          activator="parent"
      >
          <v-card>
              <v-card-text>
                À : L’équipe De : Didier le patron  Date : 02/10/2023 <br/>

Objet : Réclamation d'un employé <br/>

Cher Gisèle, <br/>

J'ai récemment été informé des préoccupations soulevées par un employé au sujet de problèmes au sein de l'équipe. Je tenais à vous en informer pour que nous puissions suivre la situation. 

Cependant, je dois dire que, selon mon point de vue, ces allégations semblent être le résultat de tensions normales dans un environnement de travail dynamique. Nous ne devrions pas surestimer ces problèmes ni y accorder une attention démesurée. Après tout, les conflits et les désaccords surviennent de temps en temps dans n'importe quelle organisation. 

Je suggère que vous traitiez cette affaire de manière discrète et que vous rassuriez l'employé concerné en lui expliquant que nous prenons tous les problèmes au sérieux. Cependant, je ne pense pas qu'il soit nécessaire de lancer une enquête approfondie à ce stade. 

Restons concentrés sur nos objectifs principaux et veillons à ce que cette situation ne perturbe pas notre activité. <br/>

Cordialement, <br/>
Didier le Patron 
              </v-card-text>
              <v-card-actions>
                  <v-btn color="primary" block @click="dialog = false">Fermer</v-btn>
              </v-card-actions>
          </v-card>
      </v-dialog>
  </v-btn>
  </div>

  
</template>

<script>
import BackToHomeButton from '@/components/BackToHomeButton.vue';
export default {
  components: {
        BackToHomeButton
    },
  data() {
    return {
      imageUrl: require('../assets/CEO.jpg'),
      dialog: false,
    };
  },
  computed: {
    backgroundImageStyle() {
      return {
        backgroundImage: `url(${this.imageUrl})`,
        backgroundSize: 'cover',
        backgroundPosition: 'center center',
      };
    },
  },
  methods: {
      openModal() {
          this.isModalOpen = true;
      },
      closeModal() {
          this.isModalOpen = false;
      },
  },
};
</script>

<style scoped>
.image-background {
  width: 100%;
  height: 100%;
}

.clickable-area {
  position: absolute; 
  top: 45vh; 
  left: 52vw;
  background-color: rgba(0, 0, 0, 0);
  color: white;
  padding: 40px;
  box-shadow: none;
}

/* clickable hover ovveride all */
  .clickable-area:hover {
      background-color: rgba(0, 0, 0, 0);
      box-shadow: none;
      cursor: default;
  }

</style>
