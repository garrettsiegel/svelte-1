<script>
  const name = 'Garrett'
  const imgLink = 'https://res.cloudinary.com/drxro4uha/image/upload/v1698250312/gangstarr-mass-appeal_2_xijheg.jpg'
</script>

<h1>Hi {name.toUpperCase()}! Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<img src={imgLink} alt="" class="image">

<style>
  .image {
    width: 100%;
    max-width: 500px;
  }
</style>