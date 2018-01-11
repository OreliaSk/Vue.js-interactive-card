<template>
	<div>
		<div class="wrapper-choosen-card">
			<div class="info">
				<p>
					<img v-bind:src="first.imgDog" v-if="!second.choosen" alt="dogInfoBubble" />
					<img v-bind:src="first.imgDog2" v-if="second.choosen" alt="dogInfoBubble" />
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
					imgDog : require('../assets/choose-card/dog_bul_1.png'),
					imgDog2 : require('../assets/choose-card/dog_bul_2.png'),
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
	/* MAIN CONTENT */
	.wrapper-choosen-card {
		align-items: center;
		background: #c9ddff;
		display: flex;
		min-height: 93vh;
		justify-content: space-around;
		width: 100%;
	}

	/* DIV WITH DOG BUBBLE INFO*/
	.info {
		align-self: flex-end;
	}
	.info img{
		height: 400px;
		width: 430px;
	}

	/* DIV WITH CARDS CHOICE */
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

