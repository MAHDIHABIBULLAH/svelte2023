<svelte:head>
  <link rel="stylesheet" href="css/main.css" />
</svelte:head>
<script>
  import Nav from "$lib/Nav.svelte";
  import Footer from "$lib/Footer.svelte";
  let name = '';
  let email = '';
  let message = '';

  function handleSubmit() {
    console.log('Name:', name);
    console.log('Email:', email);
    console.log('Message:', message);
  }
</script>
<con>
<h1>Contact Us</h1>
<form on:submit={handleSubmit}>
  <label for="name">Name:</label>
  <input type="text" id="name" bind:value={name} />

  <label for="email">Email:</label>
  <input type="email" id="email" bind:value={email} />

  <label for="message">Message:</label>
  <textarea id="message" bind:value={message}></textarea>

  <button type="submit">Submit</button>
</form>
</con>


