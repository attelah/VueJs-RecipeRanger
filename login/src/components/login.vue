<template>
    <nav class="navbar navbar-expand-lg pt-5">
        <div class="container-fluid">
            <a class="navbar-brand"><img width="50" src="../assets/chef.png"></a>
            <h1 class="display-5 text-success d-flex justify-center-content" id="header">RECIPE RANGER</h1>
            <div class="d-flex" v-bind="logger" v-if="this.logger.loggedOut">
                <input type="text" name="username" v-model="input.username" placeholder="Username" />
                <input type="password" name="password" v-model="input.password" placeholder="Password" />
                <b-button type="button" @click="login()" class="btn btn-success btn-md">Login</b-button>
            </div>
            <div v-bind="logger" v-if="this.logger.loggedIn">
                <h2>Welcome back {{account.username}}! Happy cooking! :)</h2>
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
                if (this.input.username == this.account.username && this.input.password == this.account.password) {
                    this.logger.loggedIn = true;
                    this.logger.loggedOut = false;
                } else {
                    alert("Wrong username and / or password!");
                }
            } else {
                alert("A username and password is required");
            }
        },
        logout() {
            this.logger.loggedIn = false,
                this.logger.loggedOut = true
        }
    }
};

</script>

<style scoped>

#header 
{
    font-family: fantasy;
}

/*
    #login {
        width: 500px;
        margin: auto;
        margin-top: 20px;
        padding: 10px;
    }*/
</style>