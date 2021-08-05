<template>
	<div class="footer">
		<p>This Website is <a href="https://github.com/d3r1n/d3r1n.com" target="_blank">Open Source</a>. Made with <span id="love">Love</span> by d3r1n. © Derin Önder Eren 2021</p>
	</div>
</template>

<script>
export default {
	name: "Footer"
}
</script>

<style>
.footer {
	background-color: #1f1f1f;
	border: 10px solid #39375b;
	border-radius: 25px;
	display: flex;
	justify-content: center;
	align-items: center;
	position: fixed;
	bottom: 0;
	margin-bottom: 20px;
	margin-left: 30%;
	height: 60px;
	width: 800px;
	box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
}

.footer p {
	color: #f8f8f2;
	font-size: 15px;
	margin-top: 15px;

}

.footer #love {
	color: #ff5555;
	font-size: 18px;
	font-weight: bold;
}

.footer a {
	color:#50fa7b;
	font-weight: bold;
	font-size: 18px;
}
</style>