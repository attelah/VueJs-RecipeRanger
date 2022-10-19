<template>
    <div id="add">
        <div class="container-fluid">
            <form class="d-flex">
                <input v-model="ingredient" class="form-control me-2" type="text" placeholder="Add ingredient" aria-label="Search">
                <button type="button" @click="addIngredient" class="btn btn-success btn-md" >Add</button>
            </form>
              <div class="pt-3">
                <span class="text-start h5" v-for="(ingredient, index) in ingredients" :key="index">
                    <p>- {{ingredient}}</p>
                </span>
            </div>
            
        </div>
    </div>
</template>

<script>
    export default {
        name: 'AddIngredient',
        data() {
            return {
                ingredients: [],
                ingredient: '',
            }
        },
        methods: {
            addIngredient() {
                if(this.ingredient == ""){
                    alert("You need to add an ingredient")
                } else {
                    this.ingredients.push(this.ingredient)
                    // Store to Vuex store
                    this.$store.commit('add', this.ingredients);
                    this.ingredient = "";
                }                         
            }
        }
    }
</script>
<style scoped>
.form-control:focus {
  border-color: #198754;
  box-shadow: 0px 0px 8px rgb(32, 201, 122);
}
</style>
