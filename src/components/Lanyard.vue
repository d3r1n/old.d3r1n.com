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
		<a href="https://github.com/d3r1n"><i class="fab fa-github" id="github"></i></a>
		<a href="https://open.spotify.com/user/derin9999"><i class="fab fa-spotify" id="spotifyIcon"></i></a>
		<a href="https://discord.com/users/704758931343278162"><i class="fab fa-discord" id="discord"></i></a>
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

		const quote = await ( await fetch("https://api.quotable.io/random?minLength=100&maxLength=150")).json()
		this.activity.content = quote.content
		this.activity.author = quote.author
	},
	methods: {
		toggleOpen() {
			this.isOpen = !this.isOpen
		}
	}
}
</script>