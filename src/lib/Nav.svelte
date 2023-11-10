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
  background-color: rgb(51, 51, 51);
  color: #fff4fe;
  padding: 10px 20px;
  transition: background-color 0.3s;
}

nav a:hover {
  background-color: #d8d8d8;
}
 /* Add some padding to the nav */
 .nav {
    padding: 10px;
  }

  
  /* Styling the navigation links */
  nav a {
    border-radius: 5px;
    margin: 0 5px;
  }

  /* Style the active link */
  nav a.active {
    background-color: #d8d8d8;
    color: #333;
  }

  /* Add a subtle box shadow on hover */
  nav a:hover {
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
  }

  /* Media query for responsive design */
  @media (max-width: 600px) {
    .nav {
      flex-direction: column;
      align-items: flex-start;
    }

    .yugi-logo {
      position: static;
      margin-bottom: 10px;
    }

    nav ul {
      flex-direction: column;
    }

    nav li {
      margin-bottom: 5px;
    }
  }

  </style>