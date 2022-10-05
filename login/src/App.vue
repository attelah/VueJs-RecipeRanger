<template>
<div class="body">
  <b-container class="content text-white">
    <b-row>
      <b-col> <img style="float:left" src="../src/assets/logo.png"></b-col>
      <b-col>
        <h1 style="float:left; margin-top:20px">RECIPE RANGER</h1>
      </b-col>
      <b-col>
        <div id="login">
          <Login></login>
        </div>
      </b-col>
    </b-row>
    <b-row>
      <b-col><p>Ingredients komponenten kommer här</p></b-col>
      <b-col><RecipeGetter/></b-col>
    </b-row>

    

  </b-container>
</div>
</template>
  
<script>


import Login from './components/login.vue';
import RecipeGetter from './components/RecipeGetter.vue';


export default {
  name: 'App',
  components: {
    Login,
    RecipeGetter
  }
}
</script>
  
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
  
}

#login {
  float: right;
}

body {
    background-position: center center;
    background-attachment: fixed;
    background-repeat: no-repeat; background-size: cover;
} 
@media (max-width: 480px) {
    body {
        background-image: url(./assets/cuttingboard-desk-3.jpg);
        background-position: center right;
    }
}

@media (min-width: 481px) and (max-width: 1024px) {
    body {
        background-image: url(./assets/cuttingboard-desk-3.jpg);
    }
}


@media (min-width: 1024px) {
    body {
        background-image: url(./assets/cuttingboard-desk-3.jpg);
    }
}
</style>