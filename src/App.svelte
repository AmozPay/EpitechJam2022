<script lang="ts">
	import Button from './components/Button.svelte';
	import Viken from './components/Viken.svelte';
	import vikenGenerator from './utils/viken_generator/';
	import generateHelpMeSentence from './utils/help_generator/';

	let name: string = vikenGenerator();
	let vikenDesperateCryForHelp = "Oh, that's funny";

	const change = () => {
		name = vikenGenerator();
		const [firstName, lastName] = name.split(' ');
		if (name == "Viken Kojakian")
		vikenDesperateCryForHelp = "Wow, you should play lottery, the chances were so small"
		else if (firstName === "Viken")
		vikenDesperateCryForHelp = "You got my name right, but ..."
		else if (lastName === "Kojakian")
		vikenDesperateCryForHelp = "Wow, now get my name right"
		else {
			let tmp = vikenDesperateCryForHelp;
			while (tmp === vikenDesperateCryForHelp)
				tmp = generateHelpMeSentence();
			vikenDesperateCryForHelp = tmp;
		}
	};
</script>

<main>
	<Viken text={vikenDesperateCryForHelp}></Viken>
	<div id="generator_button">
		<Button on:click={change}>Generate another name</Button>
		<h1>
			Your Viken Kojakian name is:
		</h1>
		<p class="name">{name}</p>
		<a class="external_links" href="https://lorenzo-generator.vercel.app/">Lorenzo Generator</a>
	</div>
</main>

<style>
	main {
		display: flex;
		text-align: center;
		max-width: 240px;
		flex-direction: column;
		align-items: center;
		align-content: center;
		justify-content: center;
		justify-items: center;
		margin: 0px;
		width: 100%;
		height:100%;
	}

	div {
		display: flex;
		flex-direction: column;
		align-items: center;
		align-content: center;
		justify-content: center;
		justify-items: center;
  		padding: 0px;
	}

	#generator_button {
		position: absolute;
		top: 50%;
	}

	h1 {
		font-size: 2vh;
	}

	.name {
		font-size: 5vh;
		font-weight: 700;
	}

	.external_links {
		position: absolute;
		bottom: 10px;
	}


	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>