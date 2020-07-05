<template>
  <div id="dashboard">
    <h1>That's the dashboard!</h1>
    <p>You should only get here if you're authenticated!</p>
    <!-- <p v-if="email">Your email address: {{ email }}</p> -->
    <!-- <p v-for="key in $store.getters.user.hobbies">{{key}}</p> -->
  </div>
</template>

<script>
  import axios from 'axios';

  export default {
    computed: {
      email(){
        return !this.$store.getters.user ? false : this.$store.getters.user.email
      }
    },
    created () {
      this.$store.dispatch('fetchUser')
    }
  }
</script>

<style scoped>
  h1, p {
    text-align: center;
  }

  p {
    color: red;
  }
</style>