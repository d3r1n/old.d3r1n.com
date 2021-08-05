<template>

	<div class="mainConteiner">
		<Lanyard />
		<About />
	</div>
	<Footer />
</template>

<script>

import Lanyard from "./components/Lanyard.vue"
import About from "./components/About.vue"
import Footer from "./components/Footer.vue"

export default {
  name: 'App',
  components: {
    Lanyard,
    About,
    Footer,
  }
}
</script>

<style>

</style>
