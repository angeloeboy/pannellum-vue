<template>
  <div v-if="loggedIn">
    <Lobby />
  </div>
  <div v-else>
    <Login @login="login"/>
  </div>
</template>

<script>
import Lobby from "./components/Lobby.vue"
import Login from "./components/Login.vue"

export default {
  name: 'App',
  components: {
    Lobby,
    Login
  },

  data() {
    return{
      loggedIn: false,
      userName: "",
      password: ""
    }
  },

  methods: {
    login(){
      this.loggedIn = true
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

body{
    margin: 0px;
  }
#app {
  font-family: 'Roboto', sans-serif;
  margin: 0px;
  padding: 0px;
  position: relative;
}



</style>
