<template>
    <div class="row p-3 fs-5">
        <div class="col">
            <div class="text-start form-check">
                <input class="form-check-input" type="checkbox" id="egg" value="Egg" v-model="selectedOptions" @change="sendData"/>
                <label class="form-check-label" for="egg">Egg</label>
            </div>
            <div class="text-start form-check">
                <input class="form-check-input" type="checkbox" id="meat" value="Meat" v-model="selectedOptions" @change="sendData"/>
                <label class="form-check-label" for="meat">Meat</label>
            </div>
            <div class="text-start form-check">
                <input class="form-check-input" type="checkbox" id="carrot" value="Carrot" v-model="selectedOptions" @change="sendData"/>
                <label class="form-check-label" for="carrot">Carrot</label>
            </div>
            <div class="text-start form-check">
                <input class="form-check-input" type="checkbox" id="tomato" value="Tomato" v-model="selectedOptions" @change="sendData"/>
                <label class="form-check-label" for="tomato">Tomato</label>
            </div>
            <div class="text-start form-check">
                <input class="form-check-input" type="checkbox" id="butter" value="Butter" v-model="selectedOptions" @change="sendData"/>
                <label class="form-check-label" for="butter">Butter</label>
            </div>
        </div>
        <div class="col">
            <div class="text-start form-check">
                <input class="form-check-input" type="checkbox" id="onion" value="Onion" v-model="selectedOptions" @change="sendData"/>
                <label class="form-check-label" for="onion">Onion</label>
            </div>
            <div class="text-start form-check">
                <input class="form-check-input" type="checkbox" id="garlic" value="Garlic" v-model="selectedOptions" @change="sendData"/>
                <label class="form-check-label" for="garlic">Garlic</label>
            </div>
            <div class="text-start form-check">
                <input class="form-check-input" type="checkbox" id="potato" value="Potato" v-model="selectedOptions" @change="sendData"/>
                <label class="form-check-label" for="potato">Potato</label>
            </div>
            <div class="text-start form-check">
                <input class="form-check-input" type="checkbox" id="pasta" value="Pasta" v-model="selectedOptions" @change="sendData"/>
                <label class="form-check-label" for="pasta">Pasta</label>
            </div>
            <div class="text-start form-check">
                <input class="form-check-input" type="checkbox" id="rice" value="Rice" v-model="selectedOptions" @change="sendData"/>
                <label class="form-check-label" for="rice">Rice</label>
            </div>
        </div>
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
<style scoped>
</style>

