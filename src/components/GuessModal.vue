<template>
    <v-dialog v-model="dialog" max-width="400" ref="guessModal">
        <v-card>
            <v-card-title class="headline">Devinez qui a fait quoi</v-card-title>
            <v-card-text>
                <v-select
                    v-model="who"
                    :items="['Sid', 'Gisele', 'José', 'Gilbert', 'Didier', 'Andy']"
                    label="Qui"
                ></v-select>
                <v-select
                    v-model="where"
                    :items="['Bureau de PDG', 'Salle de réunion', 'Salle de repos', 'Bureau des HR']"
                    label="Où"
                ></v-select>
                <v-select
                    v-model="what"
                    :items="['Harcèlement moral', 'Harcèlement physique', 'Aggression sexuelle', 'Aggression verbale']"
                    label="Quoi"
                ></v-select>
            </v-card-text>
            <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="primary" @click="submitGuess">Soumettre</v-btn>
            </v-card-actions>
        </v-card>
    </v-dialog>
</template>
  
<script>
const axios = require("axios");
const axiosInstance = axios.create({
  baseURL: `http://0.0.0.0:8080/api`,
});

function cleanString(input) {
    const withoutAccents = input.normalize("NFD").replace(/[\u0300-\u036f]/g, "");
    const cleanedString = withoutAccents.trim().toLowerCase();
    return cleanedString;
}

export default {
    data() {
        return {
            dialog: false,
            who: '',
            what: '',
            where: '',
        };
    },
    methods: {
        show() {
            this.dialog = true;
        },
        hide() {
            this.dialog = false;
        },
        async createUser() {
            const user = {
                nom: localStorage.getItem('playerName'),
                email: localStorage.getItem('playerEmail'),
                score: parseInt(localStorage.getItem('timeSpent') / 1000),
            };
            const response = await axiosInstance.post("/creerUtilisateur", user);
            this.sendEmail(response.data);
        },
        async sendEmail(id){
            await axiosInstance.post("/envoiMail/" + id);
        },
        verifyGuess(cleanedGuess) {
            if (cleanedGuess.who === "andy" && cleanedGuess.what === "harcelement moral" && cleanedGuess.where === "salle de reunion") {
                localStorage.setItem('endTime', new Date().getTime());
                localStorage.setItem('timeSpent', localStorage.getItem('endTime') - localStorage.getItem('gameStart'));
                this.createUser();
                this.$router.push({ name: 'scoreboard' });
            }
            else {
                alert("Mauvaise réponse");
            }
        },
        submitGuess() {
            const cleanedGuess = {
                who: cleanString(this.who),
                what: cleanString(this.what),
                where: cleanString(this.where),
            };

            this.verifyGuess(cleanedGuess);

            this.who = '';
            this.what = '';
            this.where = '';
            localStorage.clear();                     

            this.hide();
        },
    }
};
</script>

<style scoped>
.v-card-actions {
    display: flex;
    justify-content: flex-start;
    padding-left: 24px;
}
</style>
