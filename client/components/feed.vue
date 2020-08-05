<style scoped>
	*{
		font-size: 25px;
	}
	#photolenta{
		margin-top: 500px;
		background-color: green;
	}
</style>

<template>
	<div>
		<header-m></header-m>
		<photo-card v-for="record in records" v-bind:record="record"></photo-card>
	</div>
</template>

<script>
	let Header = require("./header.vue");
	let PhotoCard = require("./photoCard.vue");
	module.exports={
		components:{
			headerM: Header,
			photoCard: PhotoCard
		},
		data: function() {
			return {records: []}
		},
		mounted: function(){
			this.$http.get("/feed", {bearer: true}).then(
				function(res){
					console.log(res.body);
					this.records = res.body;
				});
		}
	}
</script>