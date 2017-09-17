<template>
	<div id="artist-list">
	    <SearchBar @artistData="artistList"/>
		
			<div class="row"  v-for="artist in data">

				<div class="col-sm-6">
					<div class="card">
						<img v-bind:src="artist.image[3]['#text']" alt="" class="card-img-top">
					</div>
			    </div>
			    <div class="col-sm-6">
			       <div class="jumbotron">
			       	  <h3>{{ artist.name }}</h3>
					  <p>{{ artist.bio.summary }}</p>
				   </div>
			    </div>

		   </div>


	</div>
</template>

<script>

import SearchBar from './SearchBar'
	
	export default {
		name: 'artist-list',
		data: function() {
			return {
				data: []
			}
		},
		template: '<SearchBar />',
		components: { SearchBar },
		methods: {
			artistList(response) {
				console.log(response);
				(response.error !== 6) ? this.data = response : this.data = [];
			}
		}
	}

</script>