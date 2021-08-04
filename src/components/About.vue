<template>
	<div class="about">
		<p id="text">
			Welcome to my website! <br />I'm <span id="about_name">d3r1n</span>,
			I'm 15 years old self-tought programmer... <br />
			I like computers, electronics, and science! <br />
			I'm also into sports. I row professionaly at <span id="gs1">Galata</span><span id="gs2">saray</span>'s Rowing Team and I like body building kinda stuff.
		</p>

		<div id="skills">
				<span v-for="skill in skillArray" :key="skill.id" :id="skill.id" class="skill">
					<a :href="skill.url" target="_blank"><p>{{ skill.name }}</p></a>
				</span>
		</div>
	</div>
</template>

<script>

let skillArray = [
	{
		name: "Python",
		url:"https://python.org/",
		id: "py"
	},
	{
		name: "Rust-lang",
		url:"https://rust-lang.org/",
		id: "rs"
	},
	{
		name: "Go-lang",
		url:"https://go-lang.com/",
		id: "go"
	},
	{
		name: "JavaScript",
		url:"https://www.w3schools.com/js/",
		id: "js"
	},
	{
		name: "TypeScript",
		url:"https://typescriptlang.org",
		id: "ts"
	},
	{
		name: "C++",
		url:"https://en.wikipedia.org/wiki/C%2B%2B",
		id: "cpp"
	},
	{
		name: "Elixir",
		url:"https://elixir-lang.org/",
		id: "ex"
	},
	{
		name: "Vue",
		url:"https://vuejs.org",
		id: "vue"
	},
	{
		name: "NodeJS",
		url:"https://nodejs.org",
		id: "node"
	},
	{
		name: "Deno",
		url:"https://deno.land",
		id: "deno"
	},
	{
		name: "SASS",
		url:"https://sass-lang.org/",
		id: "sass"
	},
	{
		name: "MongoDB",
		url:"https://www.mongodb.com/",
		id: "mongo"
	},
	{
		name: "PostgreSQL",
		url:"https://www.postgresql.org/",
		id: "psql"
	},
	{
		name: "Git",
		url:"https://git-scm.com/",
		id: "git"
	},
	{
		name: "VS Code",
		url:"https://code.visualstudio.com/",
		id: "vsc"
	},
	{
		name: "Vim",
		url:"https://www.vim.org/",
		id: "vim"
	},
	{
		name: "Docker",
		url:"https://www.docker.com/",
		id: "docker"
	},	
]

export default {
	name: "About",
	data() {
		return {
			skillArray
		}
	}
}



</script>


<style>

.about {
	margin-left: 50px;
	margin-right: 50px;
	margin-top: 50px;
	height: 700px;
	background-color: #1F1F1F;
	display: flex;
	width: 1250px;
	flex-direction: column;
	border: 10px solid #39375b;
	border-radius: 25px;
	box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
}

.about #spacer {
	display: flex;
	justify-self: center;

	width: 800px;
	height: 5px;
	border-radius: 200px;
	background-color: #44475a;

	margin-left: 200px;
}

.about #about_name {
	color: #8be9fd;
	font-size: 22px;
	font-weight: bold;
}

.about #text {
	color: #f8f8f2;
	margin-top: 20px;
	margin-left: 20px;
	font-size: 20px;
}

#skills {
	margin-left: 20px;
	height: 400px;
	margin-top: 20px;
	display: flex;
	flex-direction: row;
	overflow: auto;
	flex-wrap: wrap;
}

.skill {
	display: flex;
	border: 3px #f8f8f2 solid;
	margin:10px;
	border-radius: 15px;
	justify-content: center;
	height:75px;
	width: 150px;
	transition: all 1s ease;
	/* background: linear-gradient(45deg, rgba(247,37,133,1) 0%, rgba(72,149,239,1) 100%); */
}

.skill p {
  font-size: 20px;
  font-family: monospace;
  padding: 10px;
  padding-top:0;
  padding-bottom: 0;
  margin-top: 17px;
  color: #f5e1cb;
}

#gs1 {
	color: #ff5555;
	font-weight: bold;
}

#gs2 {
	color: #f1fa8c;
	font-weight: bold;
}

.skill:hover {
    background: linear-gradient(270deg, #fe94ff, #00197d);
    transform: rotate(10deg);
    background-size: 400% 400%;

    -webkit-animation: gradient-scroll 5s ease infinite;
    animation: gradient-scroll 5s ease infinite;
}

@-webkit-keyframes gradient-scroll {
    0%{background-position:91% 0%}
    50%{background-position:10% 100%}
    100%{background-position:91% 0%}
}
@keyframes gradient-scroll {
    0%{background-position:91% 0%}
    50%{background-position:10% 100%}
    100%{background-position:91% 0%}
}

</style>