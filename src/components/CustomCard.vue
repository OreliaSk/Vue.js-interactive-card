<template>
	<div class="bloc-preview">
		<div class="preview">
			<p>{{ preview.title }}</p>
			<p class="message">{{ preview.content }}</p>
			<p class="sender">{{ preview.sender }}</p>
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
				<div class="icons">
					<i class="fa fa-font" aria-hidden="true"></i>
					<i class="fa fa-align-justify" aria-hidden="true"></i>
					<i class="fa fa-align-center" aria-hidden="true"></i>
					<i class="fa fa-align-right" aria-hidden="true"></i>
					<i class="fa fa-align-left" aria-hidden="true"></i>
				</div>
				<textarea v-model="preview.content" cols="35" rows="5" placeholder="Veuillez entrer votre message personnalisé"></textarea>
				<div class="icons">
					<i class="fa fa-font" aria-hidden="true"></i>
					<i class="fa fa-align-justify" aria-hidden="true"></i>
					<i class="fa fa-align-center" aria-hidden="true"></i>
					<i class="fa fa-align-right" aria-hidden="true"></i>
					<i class="fa fa-align-left" aria-hidden="true"></i>
				</div>
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
					sender: '',
				},
				themes: ['Noël', 'Nouvel an', 'Anniversaire', 'Mariage', 'Naissance', 'Amitié'],

			}
		}
	}
</script>

<style>
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
}
h3 {
	padding: 0;
	margin: 0;
	font-size: 1rem;
}

</style>