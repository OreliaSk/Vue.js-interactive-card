<template>
	<div class="wrapper-custom-card">
		<div v-bind:class="preview.theme" class="preview">
			<div class="preview--opacity">
				<p class="title">{{ preview.title }}</p>
				<p class="message">{{ preview.content }}</p>
				<p class="sender">{{ preview.sender }}</p>
			</div>
		</div>

		<form class="customization">
			<div class="theme-select">
				<h3>Choisissez un thème :</h3>
				<select v-model="preview.theme">
					<option v-for="theme in themes">{{ theme }}</option>
				</select>
			</div>
			<div class="text">
				<input v-model="preview.title" type="text" placeholder="Entrez le titre de votre carte">
				<textarea v-model="preview.content" cols="35" rows="5" placeholder="Veuillez entrer votre message personnalisé"></textarea>
			</div>
			<div class="names">
				<input v-model="preview.sender" type="text" placeholder="Expéditeur de la carte" />
			</div>
			<div class="anim-checkboxes">
				<h3>Choisissez une animation :</h3>
				<input type="checkbox">
				<label>Bounce</label>
				<input type="checkbox">
				<label>Shuffle</label>
				<input type="checkbox">
				<label>Show</label>
				<input type="checkbox">
				<label>Width</label>
			</div>
			<div class="bloc-bouton"><button class="btn-send">Visualiser la carte avant envoi</button></div>
		</form>

	</div>
</template>

<script>
	export default {
		data() {
			return {
				preview: {
					title: '',
					content: '',
					theme: '',
				},
				themes: ['Noël', 'Nouvel an', 'Anniversaire', 'Mariage', 'Naissance', 'St Valentin'],
			}
		},
	}
</script>

<style>

	/* MAIN CONTENT */

	.wrapper-custom-card {
		display: flex;
		font-family: 'Lato', sans-serif;
		margin: 20px;
	}

	/* DIV PREVIEW OF CARD */

	.preview {
		border: 2px solid black;
		background-color: #fff;
		margin: 20px;
		width: 25vw;
		border-radius: 5px;
	}

	.preview--opacity {
		background-color: rgba(255, 255, 255, .7);
		margin: 20px 30px;
		border-radius: 5px;
		box-shadow: 2px 2px 2px #000;
		padding: 10px;
	}

	.title {
		text-align: center;
		font-weight: bold;
		font-size: 1.6rem;
	}
	.sender {
		text-align: right;
		font-weight: bold;
	}

	/* DIV CUSTOMIZATION CARD */

	.customization {
		margin: 20px;
	}
	.theme-select select, .names input, .text input {
		min-height: 4vh;
		padding: 5px;
		margin: 10px 5px;
		display: block;
	}
	.theme-select select {
		width: 96.5%;
	}
	.names input, .text input {
		width: 93%;
	}
	.names label, {
		display: block;
		width: 100%;
	}
	.customization textarea {
		font-family: 'Lato', sans-serif;
		font-size: .9rem;
		margin: 5px;
		padding: 10px;
	}
	.theme-select h3 {
		padding: 0;
		margin: 0;
		font-size: 1rem;
	}
	.bloc-bouton {
		margin-top: 15px;
		text-align: center;
	}
	.btn-send {
		background-color: #1758C1;
		border: none;
		border-radius: 3px;
		color: #fff;
		cursor: pointer;
		font-size: .9rem;
		padding: 7px;
	}

	/* CHANGING BACKGROUND CARD WITH COVER PROPERTY*/
	.Noël {
		background: url(../assets/custom-card/wall_noel.png) no-repeat;
		-webkit-background-size: cover;
		-moz-background-size: cover;
		-o-background-size: cover;
		background-size: cover;
	}
	.Anniversaire {
		background: url(../assets/custom-card/wall_birthday.png) no-repeat;
		-webkit-background-size: cover;
		-moz-background-size: cover;
		-o-background-size: cover;
		background-size: cover;
	}
	.Naissance {
		background: url(../assets/custom-card/wall_nais.png) no-repeat;
		-webkit-background-size: cover;
		-moz-background-size: cover;
		-o-background-size: cover;
		background-size: cover;
	}
	.Valentin {
		background: url(../assets/custom-card/wall_valentin.png) no-repeat;
		-webkit-background-size: cover;
		-moz-background-size: cover;
		-o-background-size: cover;
		background-size: cover;
	}
	.an {
		background: url(../assets/custom-card/wall_newyear.png) no-repeat;
		-webkit-background-size: cover;
		-moz-background-size: cover;
		-o-background-size: cover;
		background-size: cover;
	}
	.Mariage {
		background: url(../assets/custom-card/wall_mari.png) no-repeat;
		-webkit-background-size: cover;
		-moz-background-size: cover;
		-o-background-size: cover;
		background-size: cover;
	}

</style>