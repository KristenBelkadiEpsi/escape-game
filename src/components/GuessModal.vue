<template>
    <v-dialog v-model="dialog" max-width="400" ref="guessModal">
        <v-card>
            <v-card-title class="headline">Devinez qui a fait quoi</v-card-title>
            <v-card-text>
                <v-text-field v-model="who" label="Qui"></v-text-field>
                <v-text-field v-model="what" label="Quoi"></v-text-field>
                <v-text-field v-model="where" label="Où"></v-text-field>
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
    if (cleanedGuess.who === ".." && cleanedGuess.what === ".." && cleanedGuess.where === "..") {
        $router.push({ name: 'scoreboard' });
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