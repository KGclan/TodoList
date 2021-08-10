<template>
	<div id="app">
		<Title title="Задачник"/>
		<Main />
	</div>
</template>

<script>
import Main from "@/components/Main.vue"
import Title from "@/components/Title.vue"

export default {
	name: "App",
	components: {
		Main,
		Title
	}
}
</script>
<style lang="sass">
body
	height: 100vh
	width: 100%
	padding: 0
	margin: 0
	#app
		height: 100%
		width: 100%
		font-family: Avenir, Helvetica, Arial, sans-serif
		display: flex
		flex-direction: column
		justify-content: center
		align-items: center
</style>
