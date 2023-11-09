<script>
  let currentYear = new Date().getFullYear();

  const socialLinks = [
    { url: 'https://www.instagram.com/tetsuya_kunn/', alt: 'Instagram' },
    { url: 'https://www.snapchat.com/add/kenjiro_tsuda8', alt: 'Snapchat' },
    { url: 'https://discord.com/invite/akiyno#1230', alt: 'Discord' },
  ];
</script>

<footer>
  <div class="logo">
    <img src="img/one-piece-logo.gif" width="200" alt="Onepiece footer img">
  </div>
  <div class="container">
    <p>&copy; {currentYear} One piece. All rights reserved.</p>
  </div>
  <div class="footer-links">
    {#each socialLinks as { url, alt }}
      <a href={url} target="_blank" title={alt}>
        <img src={`img/${alt.toLowerCase()}.png`} alt={alt}>
      </a>
    {/each}
  </div>
</footer>

<style>
  /* Footer styling */
footer {
  background-color: #333;
  color: #fff;
  padding: 20px 0;
  text-align: center;
}

.logo {
  padding: 30px;
}

.footer-links {
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

.footer-links a {
  margin: 0 10px;
  text-decoration: none;
  color: #fff;
}

.footer-links img {
  width: 30px;
}
.container {
  max-width: 1200px;
  margin: 0 auto;
}

</style>