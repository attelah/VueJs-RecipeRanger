<template>
  <img style="float:left" src="../src/assets/logo.png">
  <h1 style="float:left; margin-top:30px">RECIPE RANGER</h1>
  <div id="login">
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
    margin-top: 30px;
  }
  #login {
    float:right;
  }
  </style>