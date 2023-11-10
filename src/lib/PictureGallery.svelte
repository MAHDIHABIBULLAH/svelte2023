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