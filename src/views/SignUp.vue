<script>
import axios from 'axios'
export default {
  data: function () {
    return {
      message: "Sign up here!",
      newUserParams: {}
    };
  },
  created: function () { },
  methods: {
    newUser: function () {
      console.log('new user')
      axios.post(`/users`, this.newUserParams).then(response => {
        console.log(response.data)
        this.newUserParams = response.data
      })
    }
  },
};
</script>

<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <p>Name: <input type="text" v-model="newUserParams.name"></p>
    <p>Email: <input type="email" v-model="newUserParams.email"></p>
    <p>Password: <input type="password" v-model="newUserParams.password"></p>
    <p>Password confirmation: <input type="password" v-model="newUserParams.password_confirmation"></p>
    <button v-on:click="newUser()">Sign up</button>
  </div>
</template>

<style>
</style>