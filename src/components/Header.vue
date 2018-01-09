<template>
	<nav>
		<h2>{{ title }}</h2>
	</nav>
</template>


<script>
export default {
	data(){
		return{
			title : 'Carte jolie',
		}
	}, 
}
</script>


<style scoped>
nav {
	background: crimson;
	margin: 0;
	text-align: center;
}
h2 {
	padding: 20px;
	margin: 0;
	color: #fff;
}
</style>