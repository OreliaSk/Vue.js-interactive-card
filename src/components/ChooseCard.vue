<template>
	<div>
		<div class="wrapper">
			<div class="info">
				<p>
					<img v-bind:src="first.imgDog" alt="dogInfoBubble">
				</p>
			</div>
			<div class="cards">
				<div class="card">
					<img v-for="card in second.cards" :src="card" v-on:mouseover="active=!active">
				</div>
			</div>
		</div>
		<!-- <div>Icons made by <a href="https://www.flaticon.com/authors/smashicons" title="Smashicons">Smashicons</a> from <a href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a> is licensed by <a href="http://creativecommons.org/licenses/by/3.0/" title="Creative Commons BY 3.0" target="_blank">CC 3.0 BY</a></div>-->
	</div>
</template>

<script>

export default {
	data() {
		return {
			first: {
				imgDog : require('../assets/doggycorn.png'),
			},
			second: {
				cards: [
					require('../assets/choose-card/beige.svg'),
					require('../assets/choose-card/orange.svg'),
					require('../assets/choose-card/blue.svg'),
					require('../assets/choose-card/red.svg'),
					require('../assets/choose-card/orange-blue.svg'),
					require('../assets/choose-card/green.svg'),
				]
			},
			active:false,
		}
	}
}
</script>

<style>
	.wrapper {
		height: 90vh;
		width: 100%;
		background: #ccc;
		display: flex;
		align-items: center;
		justify-content: space-around;
	}
	.info {
		border: 2px solid #000;
		align-self: flex-end;
	}
	.info img{
		height: 230px;
		width: 200px;
	}
	.cards {
		border: 2px solid red;
		justify-content: center;
		align-self: center;
	}
	.card img{
		width: 100px;
		height: 100px;
		margin: 10px;
		padding: 10px;
		cursor: pointer;
		border: 2px solid black;
	}

@keyframes animation-card {
	12.5% {transform: rotate(-5deg);}
	25% {transform: rotate(-10deg);}
	37.5% {transform: rotate(-5deg);}
	50% {transform: rotate(0deg);}
	62.5% {transform: rotate(5deg);}
	75% {transform: rotate(10deg);}
	87.5% {transform: rotate(5deg);}
	100% {transform: rotate(0deg);}
}
.card img:hover {
	animation: animation-card linear 1s infinite;
}
</style>

