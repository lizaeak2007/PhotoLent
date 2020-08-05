<style scoped>
	div{
		background: grey;
		margin: 20px;
	}
	a{
		font-size: 17px;
	}
</style>

<template>
	<div class="card" style="width: 18rem;">
		<div class="card-header">
			<h5 class="card-title">{{record.user}}</h5>
		</div>
		<img v-bind:src="'./data/' + record.file" class="card-img-top">
	</div>	
</template>

<script>
	module.exports = { props: ["record"]};
</script>