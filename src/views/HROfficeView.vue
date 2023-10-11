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
                    Je, soussigné(e) Sacha, <br/> <br/> 
                    Je souhaite déposer une déclaration formelle concernant un incident qui s'est produit le 09/10/2023 au sein de notre entreprise.  <br/> <br/> 

Lors de la réunion d'équipe du 22/09/2023, j'ai été témoin d'un comportement inapproprié de la part de mon collègue, Handy, qui m'a profondément perturbé et fait sentir mal à l'aise. Pendant la réunion, Handy a utilisé un langage offensant et des commentaires dégradants envers plusieurs membres de l'équipe, y compris moi-même.  <br/> 

Il a semblé particulièrement cibler Léa et moi-même, faisant des remarques humiliantes et insinuant que notre travail était insatisfaisant. Ses paroles étaient agressives et dénigrantes, et je me suis senti(e) attaqué(e) et dévalorisé(e) en public. <br/> <br/> 

Cette situation m'a laissé une profonde impression de malaise et d'insécurité au travail. Je crains que de tels comportements ne se reproduisent, et cela affecte sérieusement mon bien-être au sein de l'entreprise. Je suis convaincu(e) que de telles attitudes nuisent à notre productivité et à notre ambiance de travail, et je ne peux pas rester indifférent(e) à ces problèmes. <br/>

Je tiens à ce que cette déclaration soit prise en compte et que des mesures soient prises pour enquêter sur cet incident et prévenir de futurs comportements similaires. Je crois fermement en un environnement de travail respectueux et professionnel, et je veux contribuer à ce que notre entreprise continue à prospérer de manière saine et constructive. <br/><br/>

Je suis prêt(e) à coopérer pleinement avec toute enquête ou mesure que vous jugerez appropriée dans cette affaire. <br/><br/> 

Cordialement, <br/>  

Sacha  
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
        imageUrl: require('../assets/HRoffice.jpg'),
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
  