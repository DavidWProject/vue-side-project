<template>
  <div id="app">
    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/apps">Crypto-Currency</router-link>
    </nav>

    <router-view/>
  </div>
</template>

<script>
import Skills from './components/Skills.vue'
import Apps from './components/Apps.vue'

export default {
  name: 'app',
  components: {
    Skills,
    Apps
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Montserrat:400,700');

body, html {
  margin: 0;
  height: 100%;
  background-color: #549578; 
}
#app {
    width: 90%;
    height: 90%; 
}

body {
  background-color: #96cdb4; 
  font-family: 'Montserrat', sans-serif;
  display: grid;
  grid-template-rows: auto;
  justify-items: center;
  padding-top: 50px;
}

nav {
  padding: 40px 40px 40px 0;
  margin-top: -50px; 
}

nav a {
  padding: 10px;
  text-decoration: none;
  background: #fff;
  border-radius: 3px;
  color: rgb(0, 110, 255);
  font-weight: bold;
  margin-right: 15px;
}


</style>
