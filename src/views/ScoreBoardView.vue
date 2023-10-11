<template>
  <div id="app" class="container mt-5">
    <div class="scoreboard-container">
      <h1 class="scoreboard-header">Scoreboard</h1>
      <table class="scoreboard-table">
        <thead>
          <tr>
            <th>Utilisateur</th>
            <th>Temps</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="user in users" :key="user.id">
            <td>{{ user.nom }}</td>
            <td>{{ user.score }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
const axios = require("axios");
const axiosInstance = axios.create({
  baseURL: `http://127.0.0.1:8080/api`,
});
export default {
  data() {
    return {
      users: [],
    };
  },
  async mounted() {
    await this.getUsers();
  },
  methods: {
    async getUsers() {
      axiosInstance.get("/utilisateurs").then((reponse) => {
        console.log(reponse.data)
        this.users = reponse.data;
        console.log(this.users)
      });
    },
  },
};
</script>
<style>
.scoreboard-container {
  background-color: #f4f4f4;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
.scoreboard-header {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 20px;
}
.scoreboard-table {
  width: 100%;
  border-collapse: collapse;
}
.scoreboard-table th,
.scoreboard-table td {
  border: 1px solid #ccc;
  padding: 10px;
  text-align: center;
}
.scoreboard-table th {
  background-color: #333;
  color: #fff;
}
.scoreboard-table tr:nth-child(even) {
  background-color: #f2f2f2;
}
</style>
