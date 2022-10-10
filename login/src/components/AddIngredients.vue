<template>
    <div id="add">
        <div class="container-fluid">
            <form class="d-flex">
                <input v-model="ingredient" class="form-control me-2" type="text" placeholder="Add ingredient" aria-label="Search">
                <button type="button" @click="addIngredient" class="btn btn-success btn-md" >Add</button>
            </form>
            <span>{{JSON.stringify(this.ingredients)}}</span>
            
        </div>
    </div>
</template>

<script>

    export default{
        name: 'AddIngredient',
        data() {
            return {
                ingredients: [],
                ingredient: '',
            }
        },
        methods: {
            async addIngredient() {
                if(this.ingredient == ""){
                    alert("You need to add an ingredient")
                } else {
                    this.ingredients.push (this.ingredient)
                }
                
                
            }
        }
    }
</script>