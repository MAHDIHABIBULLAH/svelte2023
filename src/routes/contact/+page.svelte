<script>
  let name = '';
  let email = '';
  let message = '';

  function handleSubmit() {
    console.log('Name:', name);
    console.log('Email:', email);
    console.log('Message:', message);
  }
</script>

<con class="con">
  <h1>Contact Us</h1>
  <form on:submit={handleSubmit}>
    <label for="name">Name:</label>
    <input type="text" id="name" bind:value={name} />

    <label for="email">Email:</label>
    <input type="email" id="email" bind:value={email} />

    <label for="message">Message:</label>
    <textarea id="message" bind:value={message}></textarea>

    <div>
      <button type="submit">Submit</button>
    </div>
  </form>
</con>

<style>
  /* Contact page styling */
  .con {
    text-align: center;
    max-width: 500px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }

  label {
    display: block;
    margin-top: 1rem;
    font-weight: bold;
  }

  input,
  textarea {
    width: 100%;
    padding: 0.8rem;
    margin-top: 0.5rem;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
  }

  button {
    margin-top: 1rem;
    background-color: #007bff;
    color: #fff;
    padding: 0.8rem 1.5rem;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  button:hover {
    background-color: #0056b3;
  }
</style>
