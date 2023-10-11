<template>
    <v-dialog v-model="dialog" max-width="600">
        <v-card>
            <v-card-title class="headline">Résumé de la Situation</v-card-title>
            <v-card-text>
                <p>
                    Bienvenue dans le monde mystérieux du bureau XYZ. Plusieurs personnes travaillent ensemble dans ce
                    bureau.
                    Avant de commencer la partie, veuillez entrer votre nom et votre email ci-dessous pour personnaliser
                    votre expérience.
                </p>
                <v-text-field v-model="playerName" label="Votre nom"></v-text-field>
                <v-text-field v-model="playerEmail" label="Votre email"></v-text-field>
            </v-card-text>
            <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="primary" @click="startGame">Démarrer la Partie</v-btn>
            </v-card-actions>
        </v-card>
    </v-dialog>
</template>
  
<script>
export default {
    data() {
        return {
            dialog: false,
            playerName: '',
            playerEmail: '',
        };
    },
    methods: {
        startGame() {
            localStorage.setItem('hasSeenSummaryModal', 'true');
            localStorage.setItem('gameStart', new Date().getTime());
            localStorage.setItem('playerName', this.playerName);
            localStorage.setItem('playerEmail', this.playerEmail);
            this.$emit('start-game');
        },
    },
};
</script>
