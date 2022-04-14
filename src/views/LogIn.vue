<script>import axios from "axios";
import { response } from "express";

export default {
  data: function () {
    return {
      message: "Log in here!",
      newSessionParams: {}
    };
  },
  created: function () { },
  methods: {
    userLogin: function () {
      console.log('log in')
      axios.post(`/sessions`, this.newSessionParams).then(response => {
        console.log(response.data)
      })
    }
  },
};
</script>

<template>
  <div class="home">
    <h1>{{ message }}</h1>
  </div>
</template>

<style>
</style>