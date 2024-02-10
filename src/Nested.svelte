<script>
	import { createEventDispatcher } from "svelte"
	const dispatch = createEventDispatcher()

	function sayHello() {
		dispatch('message', { text: 'Hello!' })
	}

	let m = { x: 0, y: 0 };

	function handleMove(event) {
		m = {
			x: event.clientX,
			y: event.clientY
		};
	}
</script>

<div 
	class="box"
	on:pointermove={(e) => {
		m = { x: e.clientX, y: e.clientY }
	}} 
	
	class:color-x={m.x > 500}
	class:color-y={m.y > 200}
>
	The cursor is at {m.x} x {m.y}

	<button on:click={sayHello}>
		Click to say hello
	</button>
</div>

<style>
	.box {
		height: 50vh;
		width: 100%;
		max-width: 100vw;
		background-color: goldenrod;
		color: black;
		padding: 1rem;
		border-radius: 1rem;
		font-family: sans-serif;
		font-weight: 900;
		box-sizing: border-box;
		transition: all 0.3s ease-in-out;
	}

	.box.color-x {
		background-color: firebrick;
		color: white;
	}

	.box.color-y {
		background-color: orangered;
		color: black;
	}
</style>