<template>
    <div>
        <input type="checkbox" id="egg" value="Egg" v-model="selectedOptions">
        <label for="egg">Egg</label>
        <input type="checkbox" id="meat" value="Meat" v-model="selectedOptions">
        <label for="meat">Meat</label>
        <input type="checkbox" id="carrot" value="Carrot" v-model="selectedOptions">
        <label for="carrot">Carrot</label>
        <input type="checkbox" id="tomato" value="Tomato" v-model="selectedOptions">
        <label for="tomato">Tomato</label>
        <input type="checkbox" id="butter" value="Butter" v-model="selectedOptions">
        <label for="butter">Butter</label>
        <input type="checkbox" id="onion" value="Onion" v-model="selectedOptions">
        <label for="onion">Onion</label>
        <input type="checkbox" id="garlic" value="Garlic" v-model="selectedOptions">
        <label for="garlic">Garlic</label>
        <input type="checkbox" id="potato" value="Potato" v-model="selectedOptions">
        <label for="potato">Potato</label>
        <input type="checkbox" id="pasta" value="Pasta" v-model="selectedOptions">
        <label for="pasta">Pasta</label>
        <input type="checkbox" id="rice" value="Rice" v-model="selectedOptions">
        <label for="rice">Rice</label>
    </div>
</template>

<script>
    export default {
        name: 'CheckBoxes',
        props: {},
        components: {},
        data() {
            return {
                selectedOptions: [],
            };
        },
    };

    
</script>

