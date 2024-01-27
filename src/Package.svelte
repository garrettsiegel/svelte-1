<script>
  export let name;
  export let version;
  export let speed;
  export let website;

  $: href = `https://www.npmjs.com/package/${name}`

  let count = 0;

	function increment() {
		count += 1;
	}



  // a const named colors2 that is an array of 10 random hex colors
  const colors = Array.from({length: 10}, () => {
    const r = Math.floor(Math.random() * 255)
    const g = Math.floor(Math.random() * 255)
    const b = Math.floor(Math.random() * 255)
    return `rgb(${r}, ${g}, ${b})`
  })

  let selected = colors[0]
</script>

<h1 style="color: {selected}">Pick a color</h1>

<div>
  {#each colors as color, i}
  <button
    class="color-button"
    aria-current={selected === color}
    aria-label={`Select ${color}`}
    style={`background-color: ${color}`}
    on:click={() => selected = color}
  >
    {i + 1}
  </button>
  {/each}
</div>

<p>
  The <code>{name}</code> package is {speed} fast. Download version {version} from <a {href}>npm</a> and <a href={website}>learn more here</a>
</p>

<button on:click={increment}>
  Clicked {count} {count === 1 ? 'time' : 'times'}
</button>

{#if count > 10}
  <p>{count} is greater than 10</p>
{:else if count < 5}
  <p>{count} is less than 5</p>
{:else}
  <p>{count} is between 5 and 10</p>
{/if}


<style>
  .color-button {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    border: none;
    margin: 5px;
  }
	
</style>