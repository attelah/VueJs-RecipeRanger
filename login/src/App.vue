<template>
  <div class="body">
    <b-container class="text-white">
      <!--Navbar-->

          <LoginVue></LoginVue>

      <!--Navbar end-->

      <!--Ingredients-->
      <b-row>
        <b-col>
          <h3 class=" p-5">Ingredients</h3>
          
          <AddIngredients></AddIngredients> 

          <!--Checkboxes-->
          <div>
            <Checkbox label="Ägg" inputValue="react" v-model="selectedOptions" /><br />
            <Checkbox label="Kött" inputValue="react" v-model="selectedOptions" /><br />
            <Checkbox label="Morot" inputValue="react" v-model="selectedOptions" /><br />
            <Checkbox label="Tomat" inputValue="react" v-model="selectedOptions" /><br />
            <Checkbox label="Smör" inputValue="react" v-model="selectedOptions" /><br />
            <Checkbox label="Lök" inputValue="react" v-model="selectedOptions" /><br />
            <Checkbox label="Vitlök" inputValue="react" v-model="selectedOptions" /><br />
            <Checkbox label="Potatis" inputValue="react" v-model="selectedOptions" /><br />
            <Checkbox label="Pasta" inputValue="react" v-model="selectedOptions" /><br />
            <Checkbox label="Ris" inputValue="react" v-model="selectedOptions" />

            <br /><br /><br />

            <ul>
              <li v-for="(option, index) of selectedOptions" :key="index">
                {{ option }}
              </li>
            </ul>
          </div>
          
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

import LoginVue from './components/login.vue';
import RecipeGetter from './components/RecipeGetter.vue';
import AddIngredients from './components/AddIngredients.vue';
import Checkbox from './components/checkbox.vue';

export default {
  name: 'App',
  components: {
    LoginVue,
    RecipeGetter,
    AddIngredients,
    Checkbox
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