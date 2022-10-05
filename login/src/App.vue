<template>
  <div class="body">
    <b-container class="text-white">
      <!--Navbar-->
      <nav class="navbar navbar-expand-lg pt-5">
        <div class="container-fluid">
          <a class="navbar-brand"><img width="50" src="../src/assets/logo.png"></a>
          <h1 class="display-5">RECIPE RANGER</h1>
          
          <Login id="login"></login>
        </div>
      </nav>
      <!--Navbar end-->

      <!--Ingredients-->
      <b-row>
        <b-col>
          <h3 class=" p-5">Ingredients</h3>
          <!--Search bar-->
          <div class="container-fluid">
            <form class="d-flex">
              <input class="form-control me-2" type="search" placeholder="Add ingredient" aria-label="Search">
              <button class="btn btn-success btn-md" type="submit">Add</button>
            </form>
          </div>
          <!--Serach bar end-->
          <!--Checkboxes-->
        </b-col>
        <!--Ingredients end-->

        <!--Recipes-->
        <b-col>
          <h3 class="pt-5">Recipes</h3>
          <RecipeGetter />
        </b-col>
      </b-row>
      <!--Recipes end-->

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

/*
#login {
  float: right;
}
*/
body {
  background-position: center center;
  background-attachment: fixed;
  background-repeat: no-repeat;
  background-size: cover;
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