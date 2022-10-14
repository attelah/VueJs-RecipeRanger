<template>
    <div>
        <input type="checkbox" id="egg" value="Egg" v-model="selectedOptions" @change="sendData">
        <label for="egg">Egg</label><br />
        <input type="checkbox" id="meat" value="Meat" v-model="selectedOptions" @change="sendData">
        <label for="meat">Meat</label><br />
        <input type="checkbox" id="carrot" value="Carrot" v-model="selectedOptions" @change="sendData">
        <label for="carrot">Carrot</label><br />
        <input type="checkbox" id="tomato" value="Tomato" v-model="selectedOptions" @change="sendData">
        <label for="tomato">Tomato</label><br />
        <input type="checkbox" id="butter" value="Butter" v-model="selectedOptions" @change="sendData">
        <label for="butter">Butter</label><br />
        <input type="checkbox" id="onion" value="Onion" v-model="selectedOptions" @click="sendData">
        <label for="onion">Onion</label><br />
        <input type="checkbox" id="garlic" value="Garlic" v-model="selectedOptions" @change="sendData">
        <label for="garlic">Garlic</label><br />
        <input type="checkbox" id="potato" value="Potato" v-model="selectedOptions" @change="sendData">
        <label for="potato">Potato</label><br />
        <input type="checkbox" id="pasta" value="Pasta" v-model="selectedOptions" @change="sendData">
        <label for="pasta">Pasta</label><br />
        <input type="checkbox" id="rice" value="Rice" v-model="selectedOptions" @change="sendData">
        <label for="rice">Rice</label><br />
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
        methods: {
            sendData: function () {
                // Store to Vuex store
                this.$store.commit('addCheckBoxes', this.selectedOptions);
            }
        }
    };

    
</script>

