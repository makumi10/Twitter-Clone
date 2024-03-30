<template>
  <UserProfile/>
</template>

<script> 

import UserProfile from "./components/UserProfile.vue";

export default {
  name: 'App',
  components:{
    UserProfile
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  min-height: 100vh;
}
body{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background: #ccc;
}
</style>
