<template>
  <div id="app">
    <app-header/>
    <router-view/>
    <app-footer/>
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
<script>
import AppHeader from './components/UI/AppHeader'
import AppFooter from './components/UI/AppFooter'
import { mapActions } from 'vuex'

export default {
  components: {
    AppFooter, AppHeader
  },
  methods: mapActions(['checkAuth']),
  mounted () {
    this.checkAuth()
  }
}
</script>
