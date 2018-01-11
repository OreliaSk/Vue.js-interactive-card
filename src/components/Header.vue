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
		background-color: #1758c1;
		margin: 0;
		text-align: center;
	}
	h2 {
		color: #fff;
		font-family: 'Montserrat', sans-serif;
		letter-spacing: 2px;
		margin: 0;
		padding: 20px;	
	}
</style>