<template>

        <h1>Login</h1>
        <input type="text" name="username" v-model="input.username" placeholder="Username" />
        <input type="password" name="password" v-model="input.password" placeholder="Password" />
        <button type="button" v-on:click="login()">Login</button>
</template>

<script>
    export default {
        name: 'LoginVue',
        data() {
            return {
                input: {
                    username: "",
                    password: ""
                }
            }
        },
        methods: {
            login() {
                if(this.input.username != "" && this.input.password != "") {
                    if(this.input.username == this.$parent.testAccount.username && this.input.password == this.$parent.testAccount.password) {
                        this.$emit("authenticated", true);
                        this.$router.replace({ name: "profile" });
                    } else {
                        console.log("Wrong username and / or password!");
                    }
                } else {
                    console.log("A username and password is required");
                }
            }
        }
    }
</script>

<style scoped>
    #login {
        width: 500px;
        border: 1px solid #CCCCCC;
        background-color: #FFFFFF;
        margin: auto;
        margin-top: 200px;
        padding: 20px;
    }
</style>