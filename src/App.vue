<template>
  <div id="q-app">
    <router-view />
  </div>   
</template>

<script>
export default {
  name: 'App',
  created () {
    var config = {
      apiKey: 'AIzaSyAvK9o9MkbWeP7_V-xq8z9-FP-kjaLnhb4',
      authDomain: 'turtur-crello.firebaseapp.com',
      databaseURL: 'https://turtur-crello.firebaseio.com',
      projectId: 'turtur-crello',
      storageBucket: 'turtur-crello.appspot.com',
      messagingSenderId: '708097498736'
    }
    firebase.initializeApp(config)
  }
}
</script>

<style>
</style>
