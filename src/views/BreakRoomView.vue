<template>
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
                    "J'ai été témoin d'une situation au bureau où une personne était harcelée verbalement par un collègue. La victime semblait très mal à l'aise, mais personne n'a osé intervenir. J'ai signalé l'incident au service des ressources humaines pour espérer résoudre la situation et prévenir de futurs cas de harcèlement."
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
  export default {
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
    top: 100px; 
    left: 200px;
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
  