<template>
  <div class="body">
    <b-container class="text-white">
      <!--Navbar-->

          <LoginVue></LoginVue>

      <!--Navbar end-->
      <!--Ingredients-->
      <b-row>
        <b-col v-show="isVisible">
          <h3 class="p-5">Ingredients</h3>
          
          <AddIngredients></AddIngredients> 

          <!--Checkboxes-->
          <CheckBoxes />
          
        </b-col>
        <!--Ingredients end-->

        <!--Recipes-->
        <b-col>
          <h3 class="pt-3">Recipes</h3>
          <RecipeGetter />
          <button @click= "isVisible = !isVisible" class="btn btn-success btn-md">Hide Ingredients</button>
        </b-col>
      </b-row>
      <!--Recipes end-->

    </b-container>
  </div>
</template>
  
<script>

import LoginVue from './components/login.vue';
import RecipeGetter from './components/RecipeGetter.vue';
import AddIngredients from './components/AddIngredients.vue';
import CheckBoxes from './components/CheckBoxes.vue';

export default {
  name: 'App',
  components: {
    LoginVue,
    RecipeGetter,
    AddIngredients,
    CheckBoxes,
},

data(){
return{
  isVisible: true
}
}
};
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
    background-image: url(./assets/cuttingboard-desk-3-dark.jpg);
    background-position: center right;
  }
}

@media (min-width: 481px) and (max-width: 1024px) {
  body {
    background-image: url(./assets/cuttingboard-desk-3-dark.jpg);
  }
}


@media (min-width: 1024px) {
  body {
    background-image: url(./assets/cuttingboard-desk-3-dark.jpg);
  }
}


</style>
