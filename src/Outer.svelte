<script>
  import Nested from './Nested.svelte'
  import { createEventDispatcher } from 'svelte'

  const dispatch = createEventDispatcher()

  function forward(event) {
    dispatch('message', event.detail)
  }
</script>

<h2>Outer.svelte</h2>
<Nested on:message={forward}/>

<style>
  h2 {
    font-family: sans-serif;
    color: red;
  }
</style>