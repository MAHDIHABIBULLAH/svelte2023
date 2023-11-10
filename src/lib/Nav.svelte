<script>
  const navLinks = [
    { href: '/', text: 'One Piece' },
    { href: '/yu-gi-oh', text: 'Yu-gi-oh' },
    { href: '/contact', text: 'Contact' },
    { href: '/pictures', text: 'Pictures' }
  ];
</script>

<nav class="nav">
  <a href="/" class="nav-icon"><img src="img/onepiece.png" alt="One Piece Icon"></a>
  <div class="yugi-logo">
    <a href="/yu-gi-oh" class="nav-icon"><img src="img/yugi.png" alt="Yu-gi-oh Icon"></a>
  </div>
  <ul class="nav-list">
    {#each navLinks as { href, text }}
      <li class="nav-item"><a href={href} class="nav-link">{text}</a></li>
    {/each}
  </ul>
</nav>

<style>
  /* Base styles */
  body {
    margin: 0;
    padding: 0;
    overflow-x: hidden; /* Prevents horizontal scroll */
  }

  /* Navigation styling */
  .nav {
    background-color: #333;
    color: #fff;
    padding: 10px;
    width: 100%;
    box-sizing: border-box; /* Includes padding in the element's total width */
    display: flex;
    align-items: center;
    flex-wrap: wrap; /* Ensures nav content wraps on smaller screens */
  }

  .nav-icon img {
    width: 100%;
    max-width: 200px; /* Limits image size */
    height: auto;
  }

  .yugi-logo {
    margin-left: auto; /* Pushes the logo to the right */
  }

  .nav-list {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    width: 100%; /* Full width to contain its children */
    justify-content: space-around;
    flex-wrap: wrap; /* Allow list items to wrap */
  }

  .nav-item {
    padding: 10px;
    box-sizing: border-box;
  }

  .nav-link {
    text-decoration: none;
    color: #fff4fe;
    padding: 10px 20px;
    border-radius: 5px;
    transition: background-color 0.3s, box-shadow 0.3s;
  }

  .nav-link:hover {
    background-color: #d8d8d8;
    color: #333;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
  }

  /* Responsive design adjustments */
  @media (max-width: 600px) {
    .nav {
      flex-direction: column;
      align-items: center;
    }

    .yugi-logo, .nav-icon {
      width: 100%; /* Full width to center the images */
      display: flex;
      justify-content: center;
    }

    .nav-list {
      flex-direction: column;
      align-items: center;
    }

    .nav-link {
      width: 100%; /* Full width links on mobile */
      margin: 5px 0; /* Space out links vertically */
      text-align: center;
    }
  }
</style>
