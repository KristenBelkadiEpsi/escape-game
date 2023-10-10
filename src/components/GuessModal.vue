<template>
    <v-dialog v-model="dialog" max-width="400" ref="guessModal">
        <v-card>
            <v-card-title class="headline">Devinez qui a fait quoi</v-card-title>
            <v-card-text>
                <v-select
                    v-model="who"
                    :items="['Sid', 'Gisele', 'José', 'Léa', 'Didier', 'Andy']"
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

function cleanString(input) {
    const withoutAccents = input.normalize("NFD").replace(/[\u0300-\u036f]/g, "");
    const cleanedString = withoutAccents.trim().toLowerCase();
    return cleanedString;
}

function verifyGuess(cleanedGuess, $router) {
    console.log(cleanedGuess);
    if (cleanedGuess.who === "andy" && cleanedGuess.what === "harcelement moral" && cleanedGuess.where === "salle de reunion") {
        $router.push({ name: 'scoreboard' });
    }
    else {
        //modale d'erreur
        alert("Mauvaise réponse");
    }
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
        submitGuess() {
            const cleanedGuess = {
                who: cleanString(this.who),
                what: cleanString(this.what),
                where: cleanString(this.where),
            };

            verifyGuess(cleanedGuess, this.$router);

            // Réinitialisez les champs texte après la soumission
            this.who = '';
            this.what = '';
            this.where = '';

            // Fermez la modal
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