<template>
    <RecipeActions v-bind="RecipeActionsData" @search-recipe="searchRecipe" @next-recipe='browseRecipes("next")'
        @last-recipe='browseRecipes("back")' />
</template>
  
<script>
import RecipeActions from './RecipeActions.vue'
//import store from '../main.js'
import { apikey } from '../../apikey.js'

export default {
    name: 'RecipeGetter',
    data: function () {
        return {
            RecipeActionsData: {
                title: '',
                image: '',
                usedIngredients: '',
                missingIngredients: '',
                page: 0,
                pages: 0,
                savedRecipes: null,
                savedInstructions: [],
                instructions: ''
            }
        }
    },
    methods: {
        searchRecipe: async function () {
            // Return if no ingredients added
            if (!this.$store.storedIngredients && !this.$store.checkBoxes) return;
            if (this.RecipeActionsData.image) this.reset();
            // Get ingredients from storedIngredients store
            let addedIngredients = "";
            let checkedIngredients = "";
            for (let i = 0; i < this.$store.storedIngredients.length; i++) {
                addedIngredients += (this.$store.storedIngredients[i] + ',+');
            }
            for (let i = 0; i < this.$store.storedCheckboxes.length; i++) {
                checkedIngredients += (this.$store.storedCheckboxes[i] + ',+');
            }
            let ingredients = addedIngredients + checkedIngredients;
            console.log("Ingredients: " + ingredients);
            console.log(this.$store.storedCheckboxes);
            const options = {
                method: 'GET'
            };
            // Must await for the API response before running browseRecipes function
            await fetch('https://api.spoonacular.com/recipes/findByIngredients?apiKey=' + apikey + '&ingredients=' + ingredients + '&number=6&ignorePantry=false&ranking=1', options)
                .then(response => response.json())
                .then(response => {
                    // Saves the response to RecipeActionsData.savedRecipes to avoid unneccesary spoonacular API calls
                    this.RecipeActionsData.savedRecipes = response;
                })
                .catch(err => alert(err));

            // Get instructions from other API address
            for (let i = 0; i < this.RecipeActionsData.savedRecipes.length; i++) {
                const options = {
                    method: 'GET'
                };
                let obj = this.RecipeActionsData.savedRecipes;
                obj = JSON.parse(JSON.stringify(this.RecipeActionsData.savedRecipes));
                // Must await for the API response before running browseRecipes function
                await fetch('https://api.spoonacular.com/recipes/' + obj[i].id + '/analyzedInstructions?apiKey=' + apikey + '&', options)
                    .then(response => response.json())
                    .then(response => {
                        // Saves the response to RecipeActionsData.savedInstructions to avoid unneccesary spoonacular API calls
                        this.RecipeActionsData.savedInstructions.push(response);
                    })
                    .catch(err => alert(err));
            }

            // Open always recipe page 1 after search
            if (this.RecipeActionsData.page !== 1) this.RecipeActionsData.page = 1;
            this.browseRecipes();
        },
        browseRecipes: async function (direction) {
            // Disable buttons if no recipe has been searched.
            if (!this.RecipeActionsData.savedRecipes) return;
            // Restrict pages
            if ((direction === "next") && (this.RecipeActionsData.page < this.RecipeActionsData.savedRecipes.length)) {
                (this.RecipeActionsData.page += 1);
            }
            if ((direction === "back") && (this.RecipeActionsData.page > 1)) {
                (this.RecipeActionsData.page -= 1);
            }
            // Get the total amount of pages, to display.
            this.RecipeActionsData.pages = this.RecipeActionsData.savedRecipes.length;

            let obj = this.RecipeActionsData.savedRecipes;
            obj = JSON.parse(JSON.stringify(this.RecipeActionsData.savedRecipes));
            console.log(obj[this.RecipeActionsData.page - 1].title, obj[this.RecipeActionsData.page - 1].missedIngredients, obj[this.RecipeActionsData.page - 1].usedIngredients);

            // Reset used and missing ingredients
            this.reset();

            // Pick out all the used ingredients
            for (let i = 0; i < obj[this.RecipeActionsData.page - 1].usedIngredients.length; i++) {
                this.RecipeActionsData.usedIngredients += (obj[this.RecipeActionsData.page - 1].usedIngredients[i].amount + ' ' + obj[this.RecipeActionsData.page - 1].usedIngredients[i].unitShort + ' | ' + obj[this.RecipeActionsData.page - 1].usedIngredients[i].name + '\n');
            }
            // Pick out all the missing ingredients
            for (let i = 0; i < obj[this.RecipeActionsData.page - 1].missedIngredients.length; i++) {
                this.RecipeActionsData.missingIngredients += (obj[this.RecipeActionsData.page - 1].missedIngredients[i].amount + ' ' + obj[this.RecipeActionsData.page - 1].missedIngredients[i].unitShort + ' | ' + obj[this.RecipeActionsData.page - 1].missedIngredients[i].name + '\n');
            }
            // Get the title
            this.RecipeActionsData.title = obj[this.RecipeActionsData.page - 1].title;
            // Get the image
            this.RecipeActionsData.image = obj[this.RecipeActionsData.page - 1].image;
            // Get the instructions
            obj = this.RecipeActionsData.savedInstructions;
            obj = JSON.parse(JSON.stringify(this.RecipeActionsData.savedInstructions));

            // Picks out each line of instructions and creates a string to RecipeActionsData.instructions
            for (let l = 0; l < obj[this.RecipeActionsData.page - 1][0].steps.length; l++) {
                this.RecipeActionsData.instructions += ((l + 1) + ". " + obj[this.RecipeActionsData.page - 1][0].steps[l].step + "\n");
            }
        },
        reset: function () {
            this.RecipeActionsData.usedIngredients = '';
            this.RecipeActionsData.missingIngredients = '';
            this.RecipeActionsData.image = '';
            this.RecipeActionsData.title = '';
            this.RecipeActionsData.instructions = '';
        }

    },
    components: {
        RecipeActions
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
    margin-top: 60px;
}
</style>
  