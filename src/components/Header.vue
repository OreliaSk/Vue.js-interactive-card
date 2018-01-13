<template>
	<nav>
		<h2>{{ title | upperCase }}</h2>
		<h3>{{ subtitle }}</h3>
	</nav>
</template>


<script>
export default {
	data(){
		return{
			title : 'des cartes jolies',
			subtitle : 'Envoyez une carte faite par vos soins à vos proches, pour un événement exceptionnel !',
		}
	}, 
	filters: {
		'upperCase': function(value){
			return value.toUpperCase();
		}
	}
}
</script>


<style scoped>
	nav {
		background-color: #89b6d5;
		margin: 0;
		text-align: center;
	}
	h2, h3 {
		color: #fff;
		font-family: 'Lato', sans-serif;
		margin: 0;
	}
	h2 {
		letter-spacing: 0.05px;
		padding-top: 15px;
	}
	h3 {
		letter-spacing: 0.03px;
		padding-bottom: 15px;
		font-weight: normal;
	}
</style>