<template>
    <div id="add">
        <div class="container-fluid">
            <form class="d-flex">
                <input v-model="ingredient" class="form-control me-2" type="text" placeholder="Add ingredient" aria-label="Search">
                <button  @click="addIngredient" class="btn btn-success btn-md" >Add</button>
                
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
            addIngredient() {
                this.ingredients.push (this.ingredient)
                
            }
        }
    }
</script>