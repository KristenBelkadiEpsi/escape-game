<template>
  <div>
    <header>
      <AppNavigation></AppNavigation>
    </header>
    <div class="image-background container" :style="backgroundImageStyle">
      <div class="navigation-buttons">
        <router-link to="/salleRepos">
          <v-btn class="nav-btn" id="btn-breakRoom">Salle de Repos</v-btn>
        </router-link>
        <router-link to="/bureauPDG">
          <v-btn class="nav-btn" id="btn-CEOOffice">Bureau de PDG</v-btn>
        </router-link>
        <router-link to="/bureauRH">
          <v-btn class="nav-btn" id="btn-HROffice">Bureau des RH</v-btn>
        </router-link>
        <router-link to="/salleReunion">
          <v-btn class="nav-btn" id="btn-MeetingRoom">Salle de Réunion</v-btn>
        </router-link>
      </div>
      <div>
        <SummaryModal v-model="summaryDialog" @start-game="closeSummaryModal" />
      </div>
      <div>
        <v-btn @click="showGuessModal">Devinez Qui</v-btn>
        <GuessModal @guess-submitted="handleGuessSubmitted" ref="guessModal" />
      </div>
    </div>
  </div>
</template>

<script>
import AppNavigation from "@/components/AppNavigation.vue";
import GuessModal from "@/components/GuessModal.vue";
import SummaryModal from "@/components/SummaryModal.vue";

export default {
  name: "HomeView",
  components: {
    AppNavigation,
    GuessModal,
    SummaryModal,
  },
  data() {
    return {
      imageUrl: require("../assets/menu.jpg"),
      summaryDialog: false,
      playerName: "",
      playerEmail: "",
    };
  },
  computed: {
    backgroundImageStyle() {
      return {
        backgroundImage: `url(${this.imageUrl})`,
        backgroundSize: "cover",
        backgroundPosition: "center center",
      };
    },
  },
  created() {
    this.showSummaryModal();
  },
  methods: {
    showGuessModal() {
      this.$refs.guessModal.show();
    },
    closeGuessModal() {
      this.$refs.guessModal.hide();
    },
    showSummaryModal() {
      const hasSeenModal = localStorage.getItem("hasSeenSummaryModal");
      if (!hasSeenModal) {
        this.summaryDialog = true;
      }
    },
    closeSummaryModal() {
      this.summaryDialog = false;
    },
  },
};
</script>

<style scoped>
.image-background {
  width: 100vw;
  height: 100vh;
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center center;
}

#btn-breakRoom {
  position: absolute;
  top: 220px;
  right: 15%;
}

#btn-CEOOffice {
  position: relative;
  top: 110px;
  left: 60px;
}

#btn-MeetingRoom {
  position: absolute;
  bottom: 85px;
  left: 50%;
  transform: translateX(-50%);
}

#btn-HROffice {
  position: absolute;
  bottom: 100px;
  right: 10%;
  transform: translateX(-50%);
}

.nav-btn:hover {
  background-color: #D4AF37 !important;
}

.nav-btn {
  background-color: #0e5e0b !important;
  color: white !important;
}
</style>
