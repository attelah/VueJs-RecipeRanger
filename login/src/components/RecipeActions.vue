<template>
  <div class="recipe">
    <h1>{{ title }}</h1>
    <img :src="image" />
    <p>{{ usedIngredients }}</p>
    <p class="missing">{{ missingIngredients }}</p>
    <p>{{ instructions }}</p>
    <button @click='searchRecipe'>Search</button>
    <button @click='lastRecipe'>&lt;-</button>
    <button @click='nextRecipe'>-></button>
    <p>Page {{ page }}/{{ pages }}</p>
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
.recipe {
  white-space: pre-wrap;
}

.missing {
  color: rgb(255, 29, 29);
}

h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
