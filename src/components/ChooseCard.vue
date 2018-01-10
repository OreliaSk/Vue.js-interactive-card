<template>
	<div>
		<div class="wrapper">
			<div class="info">
				<p>
					<img v-bind:src="first.imgDog" alt="dogInfoBubble" />
				</p>
			</div>
			<div v-if="!second.choosen" class="cards">
				<div class="card">
					<img v-for="card in second.cards" :src="card" v-on:click="changeImage" />
				</div>
			</div>
			<div v-if="second.choosen" class="selection">
				coucou tout le monde !
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
				imgDog : require('../assets/chienunicorn.png'),
			},
			second: {
				cards: [
					require('../assets/choose-card/beige.svg'),
					require('../assets/choose-card/orange.svg'),
					require('../assets/choose-card/blue.svg'),
					require('../assets/choose-card/red.svg'),
					require('../assets/choose-card/orange-blue.svg'),
					require('../assets/choose-card/green.svg'),
				],
				bubble: require('../assets/choose-card/speech-bubble.svg'),
				choosen: false,
			},
		}
	},
	methods: {
		changeImage:function() {
			this.second.choosen = true;
		}
	}
}
</script>

<style>
	.wrapper {
		height: 90vh;
		width: 100%;
		background: #c9ddff;
		display: flex;
		align-items: center;
		justify-content: space-around;
	}
	.info {
		align-self: flex-end;
	}
	.info img{
		height: 400px;
		width: 430px;
	}
	.cards {
		justify-content: center;
		align-self: center;
		width: 50vw;
	}
	.card img{
		width: 150px;
		height: 150px;
		margin: 30px;
		cursor: pointer;
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

