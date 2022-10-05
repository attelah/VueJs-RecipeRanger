<template>
  <div class="recipe">
    <b-container>
      <b-row>
        <div class="image">
          <img :src="image" />
        </div>
      </b-row>
      <b-row>
        <b-col class="margin">
          <h1>{{ title }}</h1>
          <b-row class="margin">
            <h2>Ingredients</h2>
            <p>{{ usedIngredients }}</p>
            <h2>Missing ingredients</h2>
            <p class="missing">{{ missingIngredients }}<br /></p>
            <h2>Instructions</h2>
            <p>{{ instructions }}</p>
          </b-row>

        </b-col>
      </b-row>
      <b-col>
          <button @click='searchRecipe'>Search</button>
          <button @click='lastRecipe'>&lt;-</button>
          <button @click='nextRecipe'>-></button>
      </b-col>

      <b-col>
        <br />
        <p class="center">Page {{ page }}/{{ pages }}</p>
      </b-col>
    </b-container>


  </div>
</template>

<script>
export default {
  name: 'RecipeActions',
  components: {
  },
  props: {
    title: String,
    image: String,
    usedIngredients: String,
    missingIngredients: String,
    page: Number,
    pages: Number,
    savedRecipes: Object,
    savedInstructions: Array,
    instructions: String
  },
  emits: {
    'search-recipe': null,
    'next-recipe': null,
    'last-recipe': null
  },
  methods: {
    searchRecipe: function () {
      this.$emit('search-recipe')
    },
    nextRecipe: function () {
      this.$emit('next-recipe')
    },
    lastRecipe: function () {
      this.$emit('last-recipe')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.margin {
  margin-top: 20px;
}

h1 {
  font-size: large;
}
h2 {
  font-size: large;
  font-style: italic;
  text-align: left;
}

.recipe {
  white-space: pre-wrap;
}

p {
  text-align: left;
}
.center {
  text-align: center;
}

.missing {
  color: rgb(255, 29, 29);
}

img {
  max-width: 70%;
  height: auto;
  align-self: center;
}

a {
  color: #42b983;
}
</style>
