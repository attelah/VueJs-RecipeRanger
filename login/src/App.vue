<template>
  <b-container class="content">
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
</style>