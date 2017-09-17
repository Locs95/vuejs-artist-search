<template>
   <div id="search-bar" class="col-sm-12">
     
   	  <div class="form-group row">
   	  	<div class="input-group">
   	  		<input type="text" class="form-control" placeholder="search artist" v-model="query" @keyup.enter="artistSearch">
   	  		<div class="input-group-btn">
   	  			<button class="btn btn-success" @click="artistSearch">search</button>
   	  		</div>
   	  	</div>
   	  </div>

   </div>	
</template>

<script>

 import Vue from 'vue'

   export default {
   	  name: 'search-bar',
   	  data: function() {
   	  	  return {
   	  	  	 query: ''
   	  	  }
   	  },
   	  methods: {
   	  	 artistSearch() {
   	  	 	const API_KEY = 'ed8643665c40615a00558d29adc6d001';
            const URL = `http://ws.audioscrobbler.com/2.0/?method=artist.getinfo&api_key=${API_KEY}&format=json&artist=${this.query}`;
            Vue.axios.get(URL).then((response) => {
            	 this.$emit('artistData', response.data);
            });
   	  	 }
   	  }
   }

</script>

<style>
  #search-bar {
     margin-top: 20px;
     margin-bottom: 20px;
  }
</style>

