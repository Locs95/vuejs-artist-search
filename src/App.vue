<template>
  <div id="app" class="container">
    <ArtistList />
  </div>
</template>

<script>

import Vue from 'vue'
import axios from 'axios'
import VueAxios from 'vue-axios'

Vue.use(VueAxios, axios);

import ArtistList from './components/ArtistList'

  export default {
     name: 'app',
     template: '<ArtistList />',
     components : {
        ArtistList
     }
  }
</script>

<style>
  @import './assets/css/bootstrap.min.css'
</style>