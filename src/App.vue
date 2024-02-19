<template>
  <BannierePage></BannierePage>
  <UserCard></UserCard>
  <FooterPage></FooterPage>
</template>

<script>
import UserCard from './components/UserCard'
import BannierePage from './components/BannierePage.vue';
import FooterPage from './components/FooterPage.vue'

export default {
  name: 'App',
  components: {
    UserCard,
    BannierePage,
    FooterPage
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
  display: flex;
  flex-direction: column;
  align-content: center;
  align-items: center;
  justify-content: flex-start;
  
}
</style>
