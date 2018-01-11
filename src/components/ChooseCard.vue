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
				<app-customCard></app-customCard>
			</div>


		</div>
	</div>
</template>

<script>
import CustomCard from './CustomCard'
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
					require('../assets/choose-card/green.svg'),
					require('../assets/choose-card/orange-blue.svg'),
				],
				choosen: false,
			},
		}
	},
	methods: {
		changeImage:function() {
			this.second.choosen = true;
		}
	},
	components: {
		'app-customCard': CustomCard
	}
}
</script>

<style>
	.wrapper {
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

