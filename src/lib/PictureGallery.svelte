<script>
    let images = [
      "1.jpg",
      "2.jpg",
      "3.jpg",
      "4.jpg",
      "5.jpg",
      "6.jpg",
      "7.jpg",
      "8.jpg",
      "9.jpg",
      "10.jpg"
    ];
  
    let zoomedImage = null;
    function zoomImage(event, img) {
      zoomedImage = img;
      event.stopPropagation(); // Prevent the event from bubbling up to the window
    }
  
    function resetZoom() {
      zoomedImage = null;
    }
    window.addEventListener('click', resetZoom);
  </script>
  <div class="gallery" onclick="{resetZoom}">
    {#each images as img}
      <img
        src={`img/${img}`}
        alt={`Picture ${img}`}
        class:zoomed={zoomedImage === img}
        on:mouseenter="{(event) => zoomImage(event, img)}"
        on:mouseleave="{resetZoom}"
      />
    {/each}
  </div>

  <style>
    .gallery {
      display: grid;
      grid-template-columns: repeat(5, 1fr); /* 5 columns */
      grid-template-rows: repeat(2, 1fr); /* 2 rows */
      gap: 10px;
      width: 100%;
      height: 100vh; /* Adjusted to fill the vertical space */
      margin: 0;
      padding: 0;
    }
  
    .gallery img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.3s ease-in-out, z-index 0.3s ease-in-out;
      cursor: pointer;
    }
  
    .zoomed {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      z-index: 10;
      object-fit: contain;
    }
  </style>
  
  
  