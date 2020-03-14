# Svelte
#### Try At Least Once (JavaScript libraries and frameworks) > Front End Frameworks > Svelte

Official website: [https://svelte.dev](https://svelte.dev "https://svelte.dev/")

Github repository: [https://github.com/sveltejs/svelte](https://github.com/sveltejs/svelte "https://github.com/sveltejs/svelte")

------------
## What is the Svelte
Svelte is a component framework but it's not working on Virtual DOM like ReactJS or VueJS. Svelte manages everything at the compile-time. Svelte is a compiler rahter than a framework and it converts all your code into plain JavaScript code. **Cybernetically enhanced web apps!**

**ُSome features of Svelte **
- Manipulates the **real DOM** and there is **no Virtual DOM**
- Block starts with {#} and ends with {/} such as **{#if}...{/if}**
- Component codes are in the **.svelte** extension files
- Styles `<style>...</style)>` written in the Svelte files are scoped CSS
- Define a listener for a DOM event with `on:<event>` syntax. For example `on:click`

### Installation
Run these commands to make your first Svelte app

1. `$ npx degit sveltejs/template your-svelte-app-name`

1. `cd your-svelte-app-name`

1. `npm install`

1. `npm run dev`

Note: It's also possible to download the starter template as a zip file from [here](https://github.com/sveltejs/template/archive/master.zip "here").

### Quick Example
**Simple counter app**

All of the counter app is in `src\App.svelte` file which is our component. It's very simple to follow. Two main code parts in this file are observable:
- **score** variable and **addScore**, **removeScore** functions on the top between`<script>...</script>` tags
- Rest of the code which is HTML combined with Svelte and **blocked CSS** at the end

```javascript
<script>
	let score = 0;

	const addScore = ()=> score +=1;
	const removeScore = ()=> score -=1;
</script>


<div class="container">

	<h1>Welcome to Svelte</h1>

	<p class="description">
	Svelte is a radical new approach to building user interfaces. Whereas traditional frameworks like React and Vue do the bulk of their work in the browser, Svelte shifts that work into a compile step that happens when you build your app.
	</p>

	<div class="score-card">
		<span class="score-text">Score</span>
		<span class="score-value">{score}</span>

		<div>
			<button class="button" on:click={removeScore}>-</button>
			<button class="button" on:click={addScore}>+</button>
		</div>

		<span class="score-watch">
			{#if score == 0}
				Score equals zero
			{:else if score > 0}
				Score is greater than zero
			{:else}
				Score is less than zero
			{/if}
		</span>
	</div>
</div>


<style>
	.container {
		height: 100vh;
		width: 100%;
		background-image: linear-gradient( 89deg,  rgba(253,220,155,1) 26.2%, rgba(255,215,165,1) 48.5% );
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.container h1 {
		font-family: 'Pacifico', cursive;
		font-size: 3rem;
	}

	.description {
		font-size: 1.2rem;
		width: 40rem;
		max-width: 90%;
		text-align:center;

	}

	.score-card {
		width: 40rem;
		min-height: 30rem;
		margin: 1rem;
		padding: 1rem;
		background: #fff;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.score-text {
		font-size: 1.5rem;
		font-weight: 600;
	}

	.score-value {
		font-size: 6rem;
		font-weight: 600;
		color: #333;
	}

	.button {
		font-size: 3rem;
		padding: 1rem 2.5rem;
		margin: 1rem;
		border: none;
		outline: #333 dotted;
	}

	.score-watch {
		margin-top: 1rem;
		font-size: 2rem;
		font-weight: 600;
	}
</style>
```
In the command line go to project directory (try-svelte) and run `npm install` then `npm run dev` to start the app in the localhost.