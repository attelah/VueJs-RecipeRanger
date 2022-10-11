<template>
    <div>
        <CustomCheckBox label="Egg" inputValue="egg" v-model="selectedOptions" /><br />
        <CustomCheckBox label="Meat" inputValue="meat" v-model="selectedOptions" /><br />
        <CustomCheckBox label="Carrot" inputValue="carrot" v-model="selectedOptions" /><br />
        <CustomCheckBox label="Tomato" inputValue="tomato" v-model="selectedOptions" /><br />
        <CustomCheckBox label="Butter" inputValue="butter" v-model="selectedOptions" /><br />
        <CustomCheckBox label="Onion" inputValue="onion" v-model="selectedOptions" /><br />
        <CustomCheckBox label="Garlic" inputValue="garlic" v-model="selectedOptions" /><br />
        <CustomCheckBox label="Potato" inputValue="potato" v-model="selectedOptions" /><br />
        <CustomCheckBox label="Pasta" inputValue="pasta" v-model="selectedOptions" /><br />
        <CustomCheckBox label="Rice" inputValue="rice" v-model="selectedOptions" />
    
        <br /><br /><br />

        <ul>
            <li v-for="(option, index) of selectedOptions" :key="index">
             {{ option }}
            </li>
        </ul>
    </div>
</template>

<script>
    import CustomCheckBox from './CustomCheckBox.vue';

    export default {
        name: 'CheckBoxes',
        props: {},
        components: {
            CustomCheckBox,
        },
        data() {
            return {
                selectedOptions: [],
            };
        },
    };
</script>

