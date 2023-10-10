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
                  " "
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
      imageUrl: require('../assets/meetingroom.jpg'),
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
