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
 José : (soupire) "Tu sais, je ne peux plus supporter le comportement de X en réunion." <br/>

Gilbert : "Je sais exactement ce que tu veux dire. Il devient de pire en pire. À chaque fois qu'il parle, c'est comme s'il cherchait à rabaisser tout le monde." <br/>

José : "Et les insultes... Il a même osé me critiquer devant tout le monde la semaine dernière. Je n'en peux plus de ses remarques désobligeantes." <br/>

Gilbert : "Exactement. Il pense qu'il est le meilleur, qu'il sait tout mieux que nous. C'est insupportable. Et ce n'est pas seulement en réunion. Il me traite comme si j'étais incompétent dans le couloir, devant tout le monde." <br/>

José : (fronce les sourcils) "Et il a ce regard, tu sais ? Comme s'il te jugeait en permanence." <br/>

Gilbert : "Oui, c'est comme s'il voulait nous faire sentir mal. Ça me met vraiment mal à l'aise." 
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
        imageUrl: require('../assets/break_room.jpg'),
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
    top: 7vh; 
    left: 20vw;
    background-color: rgba(0, 0, 0, 0);
    color: white;
    padding: 100px;
    box-shadow: none;
  }

  /* clickable hover ovveride all */
    .clickable-area:hover {
        background-color: rgba(0, 0, 0, 0);
        box-shadow: none;
        cursor: default;
    }
  
  </style>
  