<script>
    import PictureGallery from "$lib/PictureGallery.svelte";
  </script>
  
  <main>
    <h1>Picture Gallery</h1>
    <PictureGallery />
  </main>
  
  <style>
    main {
      max-width: 60%;
      margin: auto;
      text-align: center;
    }
  
    @keyframes fadeIn {
      from {
        opacity: 0;
      }
      to {
        opacity: 1;
      }
    }
  
    h1 {
      font-family: 'Arial', sans-serif;
      color: #333;
      margin: 0;
      padding: 20px 0;
      font-size: 2.5rem;
      text-transform: uppercase;
      letter-spacing: 1px;
      animation: fadeIn 1s ease-out forwards;
      transition: color 0.3s ease; /* Transition for the color change on hover */
    }
  
    h1:hover {
      color: #555; /* Darker shade when hovered */
    }
  </style>
  