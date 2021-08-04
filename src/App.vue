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
  }
}
</script>

<style>

</style>
