<script>
  const text = `Lorem ipsum dolor sit amet consectetur adipisicing elit. Autem cumque doloribus id <strong>exercitationem</strong> quam suscipit architecto alias odio? Aliquam, ipsum!`

  let count = 0;
  $: doubled = count * 2
  $: {
    console.log(`the count is ${count}`)
    console.log(`the ${count} doubled is ${doubled}`)
  }

  $: if (count >= 10) {
    console.log(`${count} is dangerously high!`)
  }

  function handleClick() {
    count += 1
  }

  let numbers = [1, 2, 3, 4, 5]

  function addNumber() {
    numbers = [...numbers, numbers.length + 1]
  }

  $: sum = numbers.reduce((total, num) => total + num, 0)

</script>

<p>{@html text}</p>

<button on:click={handleClick}>
  Clicked {count} {count === 1 ? 'time' : 'times'}
</button>

<p>{count} doubled is {doubled}</p>



<p>{numbers.join(' + ')} = {sum}</p>
<p>{numbers} - {numbers.length}</p>
<button on:click={addNumber}>
  Add a number
</button>