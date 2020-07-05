<template>
  <div id="app">
    <app-header></app-header>
    <router-view></router-view>
  </div>
</template>

<script>
  import AppHeader from './components/header/header.vue'
  
  export default {
    name: 'app',
    components: {
      AppHeader
    },
    created(){
      this.$store.dispatch('tryAutoLogin')
    }
  }
</script>

<style>
  body, html {
    margin: 0;
    font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  }
</style>