<template>
  <div id="app">
    <landing-page></landing-page>
  </div>
</template>

<script>
import landingPage from './components/portfolio/landingPage.vue'

export default {
  name: 'App',
  components: {
    landingPage
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
<style lang="scss">@import './assets/styles/theme.scss'</style>
