<template>
	<div id="modal" @click="toggleOpen">
		<div id="spotify" >
			<span id="art">
				<img :src="obj.album_art_url" :alt="obj.album">
			</span>
			<span class="info" @click="openSpotify(obj.track_id)">
				<p id="song">Listening to {{ obj.song }}</p>
				<p id="artist">By {{ obj.artist }}</p>
				<p id="album">In {{ obj.album }}</p>
			</span>
		</div>
	</div>

</template>

<script>
export default {
	name:"PopUp",
	props: ["obj", "toggleOpen"],
	methods: {
		openSpotify(id) {

			window.open("https://open.spotify.com/track/" + id + "/");

		}
	}

}
</script>

<style>

#modal {
	position: absolute;
	display: flex;
	justify-content: center;
	justify-self: center;
	background-color: rgba(18, 21, 37, 0.9);
	top:0;
	left:0;
	z-index: 5;
	width: 100%;
	height: 100%;
}

#spotify {
	cursor: pointer;
	display: flex;
	align-items: center;
	justify-content: center;
	width :750px;
	height: 300px;
	border: 10px solid #44475a;
	border-radius: 50px;
	margin-top: 250px;
	background: #282a36;
}

#art img {
	height: 200px;
	width: 200px;
	border-radius: 25px;
	margin-right: min(25px);
	margin-left: min(25px);

}

.info {
	display: flex;
	justify-content: center;
	min-width: 400px;
	max-width: 450px;
	flex-direction: column;
	margin-left: 0px;
}

#song {
	font-size: 25px;
	text-decoration: underline;
	text-decoration-color: #f8f8f2;
	color: #f8f8f2;
}

#artist {
	font-size: 20px;
	text-decoration: underline;
	text-decoration-color: #ffb86c;
	color: #ffb86c;
}

#album {
	font-size: 20px;
		text-decoration: underline;
	text-decoration-color: #bd93f9;
	color: #bd93f9;
}


</style>