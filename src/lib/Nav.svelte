<script>
    let currentYear = new Date().getFullYear();
  
    const navLinks = [
      { href: '/', text: 'One Piece' },
      { href: '/yu-gi-oh', text: 'Yu-gi-oh' },
      { href: '/contact', text: 'Contact' },
    ];
  </script>
  
  <nav class="nav">
    <img src="img/onepiece.png" width="200" alt="One Piece Icon">
    <div class="yugi-logo">
      <img src="img/yugi.png" width="200" alt="Yu-gi-oh Icon">
    </div>
    <ul>
      {#each navLinks as { href, text }}
        <li><a href={href}>{text}</a></li>
      {/each}
    </ul>
  </nav>
  