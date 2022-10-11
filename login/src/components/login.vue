<template>
    <nav class="navbar navbar-expand-lg pt-5">
        <div class="container-fluid">
            <a class="navbar-brand"><img width="50" src="../assets/logo.png"></a>
            <h1 class="display-5">RECIPE RANGER</h1>
            <div v-bind="logger" v-if="LoggedOut">
                <input type="text" name="username" v-model="input.username" placeholder="Username" />
                <input type="password" name="password" v-model="input.password" placeholder="Password" />
                <b-button type="button" @click="login()">Login</b-button>
            </div>
            <div v-bind="logger" v-if="loggedIn">
                <h2>Welcome back {{account.username}}!</h2>
                <b-button type="button" @click="logout()">Logout</b-button>
            </div>
        </div>
    </nav>
</template>

<script>

export default {
    name: 'LoginVue',
    data() {
        return {
            logger: {
                loggedIn: false,
                loggedOut: true,
            },
            input: {
                username: "",
                password: "",
            },
            account: {
                username: "DemoRanger",
                password: "password123",
                message: "Welcome back DemoRanger! Happy cooking! :)"
            },
        }
    },
    methods: {
        login() {
            if (this.input.username != "" && this.input.password != "") {
                if (this.input.username == this.logger.DemoUser && this.input.password == this.logger.password) {
                    this.loggedIn = true;
                    this.loggedOut = false;
                } else {
                    alert("Wrong username and / or password!");
                }
            } else {
                alert("A username and password is required");
            }
        },
        logout() {
            this.loggedIn = false,
                this.loggedOut = true
        }
    }
};

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