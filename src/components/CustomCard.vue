<template>
	<div class="wrapper-custom-card">
		<div v-bind:class="preview.theme" class="preview">
			<div class="preview--opacity">
				<p v-bind:class="font" class="title">{{ preview.title}}</p>
				<p v-bind:class="font" class="message">{{ preview.content }}</p>
				<p v-bind:class="font" class="sender">{{ preview.sender }}</p>
			</div>
		</div>

		<form class="customization">
			<div class="theme-select">
				<h3>Choisissez un thème :</h3>
				<select v-model="preview.theme" selected>
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
			<div class="anim-select">
				<h3>Choisissez une animation :</h3>
				<select v-model="animation">
					<option v-for="animation in animations">{{animation}}</option>
				</select>
			</div>
			<div class="fonts">
				<h3>Choisissez une police :</h3>
				<select v-model="font">
					<option v-for="font in fonts">{{font}}</option>
				</select>
			</div>
			<div class="bloc-bouton">
				<button class="btn-send">Visualiser la carte avant envoi</button>
			</div>
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
					font:'',
					animation: '',
				},
				themes: ['Noël', 'Nouvel an', 'Anniversaire', 'Mariage', 'Naissance', 'St Valentin'],
				fonts: ['Pacifico', 'Didact Gothic', 'Playfair Display', 'Handlee'],
				animations: ['Bounce', 'Shuffle', 'Show', 'Width'],
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
	.theme-select select, .names input, .text input, .fonts select, .anim-select select {
		min-height: 4vh;
		padding: 5px;
		margin: 10px 5px;
		display: block;
	}
	.theme-select select, .fonts select, .anim-select select {
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
	h3 {
		padding: 0 0 0 7px;
		margin: 0;
		font-size: 1rem;
	}

	/* style buttons */
	.btn-font {
		border: none;
		border-radius: 4px;
		cursor: pointer;
		font-size: 1rem;
		margin-right: 5px;
		transition: all .3s linear;
	}
	.btn-font:hover {
		background-color: rgba(23, 88, 193, .25);
	}
	.Pacifico {
		font-family: 'Pacifico', cursive;
		padding: 5px;
	}
	.Gothic {
		font-family: 'Didact Gothic', sans-serif;
		padding: 10.2px;
	}
	.Playfair {
		font-family: 'Playfair Display', serif;
		padding: 10.2px;
	}
	.Handlee {
		font-family: 'Handlee', cursive;
		padding: 8px;
	}
	.bloc-bouton {
		margin-top: 15px;
		text-align: center;
	}
	.btn-send {
		background-color: #1758C1;
		border:none;
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