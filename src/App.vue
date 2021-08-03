<template>

	<div class="mainConteiner">
		<Lanyard />
		<About />
	</div>

</template>

<script>

import Lanyard from "./components/Lanyard.vue"
import About from "./components/About.vue"

export default {
  name: 'App',
  components: {
    Lanyard,
    About,
  },
  data() {
		return { 
			avatar: String,
			username: String,
			tag: String,
			description: String,
			color: "#50fa7b",
		}
  },
  async mounted() {
	  	const { data } = await (await fetch("https://api.lanyard.rest/v1/users/704758931343278162")).json()
		this.avatar = `https://cdn.discordapp.com/avatars/${data.discord_user.id}/${data.discord_user.avatar}.png?size=512`
		this.username = data.discord_user.username
		this.tag = data.discord_user.discriminator
		this.description = "d3r1n's website. Welcome!"

		document.getElementById("ogtitle").setAttribute("content", this.username + "#" + this.tag)
		document.getElementById("ogimage").setAttribute("content", this.avatar)
		document.getElementById("ogdescription").setAttribute("content", this.description)
		document.getElementById("ogcolor").setAttribute("content", this.color)
		document.getElementById("ogicon").setAttribute("content", this.avatar)
  }
}
</script>

<style>

</style>
