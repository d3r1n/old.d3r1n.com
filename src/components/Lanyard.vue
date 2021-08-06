<template>
  <div v-if="Object.keys(lanyard).length" id="profile_card">

	<span :id="status"></span>

	<span id="spotify-btn" @click="toggleOpen" v-if="lanyard.spotify != null"><i class="fas fa-music"></i></span>

	<div id="avatar">
		<img :src="`https://cdn.discordapp.com/avatars/${lanyard.discord_user.id}/${lanyard.discord_user.avatar}.png?size=512`" alt="Discord Avatar">
	</div>

	<div id="name">
		<span id="name__text">{{lanyard.discord_user.username}}<span id="name__tag">#{{lanyard.discord_user.discriminator}}</span></span>
		
	</div>

	<span id="spacer"></span>

	<div id="presence">
		<p id="content">{{ activity.content }}</p>
		<p id="author">- {{ activity.author }}</p>
	</div>

	<div id="links">
		<a href="https://github.com/d3r1n" target="_blank"><i class="fab fa-github" id="github"></i></a>
		<a href="https://open.spotify.com/user/derin9999" target="_blank"><i class="fab fa-spotify" id="spotifyIcon"></i></a>
		<a href="https://discord.com/users/704758931343278162" target="_blank"><i class="fab fa-discord" id="discord"></i></a>
	</div>

  </div>

  <PopUp :obj="lanyard.spotify" :toggleOpen="toggleOpen" v-if="isOpen" />
</template>

<script>

import PopUp from "./PopUp.vue"

export default {
	name: 'Lanyard',
	data() {
		return {
			lanyard: {},
			status: "offline",
			activity: {},
			isOpen: false,
		}
	},
	components: {
		PopUp
	},
	async mounted() {
		const { data } = await (await fetch("https://api.lanyard.rest/v1/users/704758931343278162")).json()
		this.lanyard = data || {}
		
		if (this.lanyard.discord_status == "online") {
			this.status = "online"
		}
		else if (this.lanyard.discord_status == "dnd") {
			this.status = "dnd"
		}
		else if (this.lanyard.discord_status == "idle") {
			this.status = "idle"
		}
		else {
			this.status = "offline"
		}

		const quote = await ( await fetch("https://api.quotable.io/random?minLength=100&maxLength=150")).json()
		this.activity.content = quote.content
		this.activity.author = quote.author

		document.getElementById("favicon").setAttribute("href", `https://cdn.discordapp.com/avatars/${this.lanyard.discord_user.id}/${this.lanyard.discord_user.avatar}.png?size=512`)
		// <link rel="icon" type="image/png" href="https://example.com/favicon.png"/>
	},
	methods: {
		toggleOpen() {
			this.isOpen = !this.isOpen
		}
	}
}
</script>