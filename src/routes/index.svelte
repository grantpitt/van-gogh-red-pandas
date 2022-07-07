<script lang="ts">
	import pandaImageId from "../assets/pandas.json";
	const models = ["mini", "mega", "mega-full"] as const;
</script>

<main>
	<h1>Van Gogh red pandas</h1>

	{#each models as model}
		<h2>{model}</h2>
		<article>
			{#each pandaImageId[model] as imageId}
				<img
					loading="lazy"
					src="panda-imgs/{model}/a van gogh painting of a red panda::{imageId}.jpeg"
					alt="a van gogh painting of a red panda"
				/>
			{/each}
		</article>
	{/each}
</main>

<style>
	@import url("https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;700&display=swap");

	:global(body) {
		font-family: "IBM Plex Mono", monospace;
		background-color: #111;
		color: #eee;
		margin: 0;
		padding: 0;
	}

  main {
    margin: 2rem 4vw;
  }

	h1 {
		font-size: 2.5rem;
		font-weight: 700;
		margin-bottom: 1rem;
	}

	h2 {
		font-weight: 400;
		font-size: 1.5rem;
	}

	article {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    margin-bottom: 3rem;
	}

	img {
		width: 100%;
		height: auto;
	}
</style>
