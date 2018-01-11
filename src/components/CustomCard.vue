<template>
	<div class="bloc-preview">
		<div v-bind:class="preview.theme" class="preview">
			<div class="preview--opacity">
				<p class="title">{{ preview.title }}</p>
				<p class="message">{{ preview.content }}</p>
				<p class="sender">{{ preview.sender }}</p>
			</div>
		</div>
		<form class="customization">
			<div class="theme-checkboxes">
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
			<button class="btn-send">Visualiser la carte avant envoi</button>
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
.title {
	text-align: center;
	font-weight: bold;
	font-size: 1.6rem;
}
.sender {
	text-align: right;
	font-weight: bold;
}
* {
	font-family: 'Lato', sans-serif;
}
.bloc-preview {
	display: flex;
	margin: 20px;
}
.preview {
	border: 2px solid black;
	background-color: #fff;
	margin: 20px;
	width: 25vw;
	border-radius: 5px;
}
.customization {
	margin: 20px;
}
.names label, .names input{
	display: block;
	width: 100%;
}
.text input {
	display: block;
	width: 94%;
}
.customization input {
	min-height: 4vh;
	padding: 5px;
	margin: 5px;
}
.customization textarea {
	margin: 5px;
	padding: 10px;
}
h3 {
	padding: 0;
	margin: 0;
	font-size: 1rem;
}

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
.preview--opacity {
	background-color: rgba(255, 255, 255, .7);
	margin: 20px 30px;
	border-radius: 5px;
	box-shadow: 2px 2px 2px #000;
	padding: 10px;
}

</style>