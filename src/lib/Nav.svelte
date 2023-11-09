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
  
  <style>


/* Navigation styling */
.nav {
  margin: 0;
  background-color: #333;
  color: #fff;
  position: relative;
  width: 100%;
}

.yugi-logo {
  position: absolute;
  top: 0;
  right: 0;
}

.nav ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 50px;
}

nav li {
  text-align: center;
}

nav a {
  text-decoration: none;
  background-color: #333;
  color: #416463;
  padding: 10px 20px;
  transition: background-color 0.3s;
}

nav a:hover {
  background-color: #d8d8d8;
}


  </style>