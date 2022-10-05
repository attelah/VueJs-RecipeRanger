<template>
  <img src="../src/assets/logo.png">
  <div id="login">
  <h1>RECIPE RANGER</h1>
            <Login ></login>
            </div>
  
  </template>
  
  <script>


import Login from './components/login.vue';

  
  export default {
    name: 'App',
    components: {
    Login

}
  }
  </script>
  
  <style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  #login {
    float:right;
  }
  </style>