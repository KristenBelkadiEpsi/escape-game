<template>
    <nav class="navbar sticky-top bg-light">
      <div class="container-fluid">
      <div class='row' id="row-navbar">
        <div class='col-3'>
          <button class="navbar-toggler dropDownButton" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
        </div>
        <div class='col-2 p-2'>
        <a aria-current="page" href="/"><img class='icon' alt="logo" src="@/assets/key.png"></a>
        </div>
        <div class='col-7'>
          <p class='text'>Escape ton harcèlement</p>
        </div>
      </div>
      </div>
       <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav mb-2 mb-lg-0">
            <li class="nav-item">
              <router-link to='/' class="nav-link">Accueil</router-link>
            </li>
            <li class="nav-item">
              <router-link to='/reglesJeu' class="nav-link">Règles du jeu</router-link>
            </li>
            <li class="nav-item">
                <a href="https://www.service-public.fr/particuliers/vosdroits/F2354" class="nav-link">En savoir plus</a>
            </li>
          </ul>
        </div>
    </nav> 
</template>
    
<script>
    export default {
    data() {
        return {
        showMenu:false
        }
    },
    methods: {
        toggleShowMenu() {
        if (this.showMenu == false){
            this.showMenu=true;
        } else {
            this.showMenu = false;
        }
        }
    }
    }
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Barlow+Condensed&display=swap');

.navbar {
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    -moz-box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    -webkit-box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}
.icon {
    padding-left: .5em;
}
.icon2 {
  max-height:  30px;
  padding-left: 2.5em;
}
.dropDownButton{
    height: 100%;
    width: 200%;
    margin-left: -20%;
    border:none;
}
.text{
    margin-top: 10px;
    margin-left: -10px;
    font-family:'Barlow Condensed';
    font-size: 30px;
    padding-left: .3em;
    color: #0D4205;
}
nav a {
  font-weight:500;
  text-align: center;
  color: #2c3e50;
}
.nav-link{
  font-size: 17px;
  color: #0e5e0b;
}
.nav-link:hover{
  background-color: #0e5e0b;
  color: white;
}
#row-navbar {
    width: 60%;
}
</style>