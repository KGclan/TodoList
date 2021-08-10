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
	@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@200;400;500;600;800&display=swap')
	
	body
		height: 100vh
		width: 100%
		padding: 0
		margin: 0
		font-family: 'Montserrat', sans-serif
		#app
			height: 100%
			width: 100%
			display: flex
			flex-direction: column
			justify-content: center
			align-items: center
</style>
