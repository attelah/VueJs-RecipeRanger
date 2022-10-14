<template>
  <div class="recipe">
    <b-container>
      <b-row>
        <b-col class="margin fixed">
          <h2 v-if="image">{{ title }}   <img :src="image"/></h2>
          <b-row class="margin" v-if="image">
            <h4 class="p5">Ingredients</h4>
            <p>{{ usedIngredients }}</p>
            <h4>Missing ingredients</h4>
            <p class="missing">{{ missingIngredients }}<br /></p>
            <h4>Instructions</h4>
            <p>{{ instructions }}</p>
          </b-row>

        </b-col>
      </b-row>
      <b-col>
          <b-button @click='searchRecipe' class="btn btn-success">Search</b-button>
          <b-button v-if="image" @click='lastRecipe' class="btn btn-success">&lt;-</b-button>
          <b-button v-if="image" @click='nextRecipe' class="btn btn-success">-></b-button>
      </b-col>

      <b-col>
        <br />
        <p class="center" v-if="image">Page {{ page }}/{{ pages }}</p>
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

h4 {
  text-align: left;
  text-decoration: underline;
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
  color: rgb(255, 52, 52);
}

img {
  align-self: center;
  width: 100px;
  height: 100px;
  object-fit: cover;
}

a {
  color: #42b983;
}
</style>
