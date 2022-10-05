<template>
  <img style="float:left" src="../src/assets/logo.png">
  <h1 style="float:left; margin-top:20px">RECIPE RANGER</h1>
  <div id="login">
    <Login></login>
  </div>
  <RecipeGetter/>

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