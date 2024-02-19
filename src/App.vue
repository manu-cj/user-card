<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <UserCard msg="Welcome to Your Vue.js App"/>
</template>

<script>
import UserCard from './components/UserCard'

export default {
  name: 'App',
  components: {
    UserCard
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
</style>
