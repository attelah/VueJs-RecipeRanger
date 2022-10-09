<template>

        <h1>{{title}}</h1>
            
</template>

<script>
    export default {
        name: 'profile-vue',     
        props:['title', 'content']
            };     
</script>

<style scoped>
    #secure {
        background-color: #af1896;
        border: 1px solid #020000;
        padding: 20px;
        margin-top: 10px;
    }
</style>