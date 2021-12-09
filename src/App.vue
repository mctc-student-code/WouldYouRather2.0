<template>
	<div id="app">
		<h1>Would you rather?</h1>

		<would-you-rather
			v-for="question in questions"
			v-bind:key="question.id"
			v-bind:question="question.question"
			v-bind:id="question.id"
			v-bind:answer1="question.answer1"
			v-bind:answer2="question.answer2"
			v-on:user-chose="userChose"
		>
		</would-you-rather>

		<p class="you-would-rather">You would rather</p>

		<ul id="usersChoices">
			<li v-for="choice in usersChoices">
				{{ choice }}
			</li>
		</ul>
	</div>
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
	name: 'App',
	components: {
		WouldYouRather,
	},
	data() {
		return {
			questions: [
				{
					id: 0,
					question: 'Would you rather be a robot or a cyborg?',
					answer1: 'robot',
					answer2: 'Cyborg',
				},
				{
					id: 1,
					question:
						'Would you rather be rich and unknown or famous but not rich?',
					answer1: 'Rich and unknown',
					answer2: 'Famous but not rich',
				},
				{
					id: 2,
					question: 'Would you rather swim in Jell-O or swim in Nutella?',
					answer1: 'Jell-o',
					answer2: 'Nutella',
				},
			],

			usersChoices: [],
		}
	},
	methods: {
		userChose(choice, id) {
			this.usersChoices[id] = choice
		},
	},
}
</script>

<style>
.you-would-rather {
	font-family: impact;
	font-style: italic;
	margin-bottom: 20px;
}

body {
	background: burlywood;
}
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	margin-top: 60px;
}
h1 {
	font-style: oblique;
	text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000,
		1px 1px 0 #000;
}
p {
	font-size: 45px;
	font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
	color: black;
}
p:hover {
	color: lime;
	font-style: italic;
	text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000,
		1px 1px 0 #000;
	text-decoration: underline;
	text-decoration-color: orangered;
}
</style>
