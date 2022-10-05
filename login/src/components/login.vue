<template>


    <div id="login">
        <input type="text" name="username" v-model="input.username" placeholder="Username" />
        <input type="password" name="password" v-model="input.password" placeholder="Password" />
        <button type="button" v-on:click="login()" >Login</button>
            <h2 v-show="isVisible">{{ message }}</h2>
    </div>
</template>

<script>
    
    

    export default {
        name: 'LoginVue',
        data() {
            return {
                input: {
                    username: "",
                    password: "",
                },/*
                demoAccount:{
                    username: "DemoRanger",
                    password: "password123",
                },
                message:{
                    message: "Welcome back " + this.demoAccount.username +"!",
                    isVisible: false
                }*/
            }
        },
        methods: {
            login() {
                if(this.input.username != "" && this.input.password == "") {
                    if(this.input.username == this.demoAccount.username && this.input.password == this.demoAccount.password) {
                        this.message.isVisible = true;
                        
                    } else {
                        alert("Wrong username and / or password!");
                    }
                } else {
                    alert("A username and password is required");
                }
            }
        }
        
    }
</script>

<style scoped>
    /*
    #login {
        width: 500px;
        margin: auto;
        margin-top: 20px;
        padding: 10px;
    }*/
</style>