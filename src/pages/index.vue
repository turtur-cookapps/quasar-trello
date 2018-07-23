<template>
  <q-page class="row justify-center">
    <div class="center-container">
      <div>
        <h2 style="text-align:center">Welcome to Crello!</h2>
      </div>
      <div>
        <h3 style="text-align:center">Log in to Crello</h3>
      </div>
      <div id="firebaseui-auth-container">
        {{ createLoginButtons() }}
      </div> 
    </div>  
  </q-page>
</template>

<style>
</style>

<script>

import firebase from 'firebase'
import firebaseui from 'firebaseui'
import '../../node_modules/firebaseui/dist/firebaseui.css'

export default {
  name: 'Login',
  methods: {
    createLoginButtons () {
      var config = {
        callbacks: {
          signInSuccessWithAuthResult: (authResult, redirectUrl) => {
            return true
          }
        },
        signInFlow: 'popup',
        signInSuccessUrl: 'https://turtur-crello.firebaseapp.com',
        signInOptions: [
          firebase.auth.GoogleAuthProvider.PROVIDER_ID,
          firebase.auth.EmailAuthProvider.PROVIDER_ID
        ]
      }
      var ui = new firebaseui.auth.AuthUI(firebase.auth())
      ui.start('#firebaseui-auth-container', config)
    }
  }
}
</script>



<style lang="stylus">
@import '~variables'
.center-container
  h3
    padding-bottom 4px
    border-bottom 1px solid rgba(200, 0, 0, .2)
  h2
    padding 10px 15px
    background rgba(86,61,124,.05)
    border 1px solid rgba(86,61,124,.2)
</style>
