<template>
	<div class="wyr">
		<h3>{{ question }}</h3>

		<input
			type="radio"
			v-model="choice"
			v-bind:value="answer1"
			v-on:change="choiceMade"/>
		<label>{{ answer1 }}</label>

		<input
			type="radio"
			v-model="choice"
			v-bind:value="answer2"
			v-on:change="choiceMade"/>

		<label>{{ answer2 }}</label>
	</div>
</template>

<script>
export default {
	name: 'WouldYouRather',

	props: {
		question: String,
		answer1: String,
		answer2: String,
	},
	data() {
		return {
			choice: '',
		}
	},
	methods: {
		choiceMade() {
			this.$emit('user-chose', this.choice)
		},
	},
}
</script>

<style>
h2 {
	font-size: 13px;
}

h3 {
	margin: 40px 0 0;
}
.wyr {
	border: 2px black solid;
	background: orangered;
}
.wyr:hover h3 {
	font-size: 30px;
	font-family: arial;
	color: white;
	text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000,
		1px 1px 0 #000;
	transform: scale(1) rotate(0deg) translate(0px, 0px) skew(20deg, 0deg);
}
h2 {
	color: white;
	font-size: 14px;
	font-variant: small-caps;
}
.wyr:hover h2 {
	text-decoration: underline;
	color: black;
}
h3 {
	line-height: 30px;
	margin-top: 20px;
	margin-bottom: 10px;
	color: white;
	transform: scale(1) rotate(0deg) translate(0px, 0px) skew(30deg, 0deg);
	font-size: 30px;
}
</style>
