<script>
  import { onMount } from 'svelte';
  
let cardData = [];

async function fetchCardData() {
  try {
    const response = await fetch('https://db.ygoprodeck.com/api/v7/cardinfo.php');
    const result = await response.json();
    cardData = result.data;
  } catch (error) {
    console.error('Error fetching card data:', error);
  }
}


<svelte:head>
    <link rel="stylesheet" href="css/main.css"/>
</svelte:head>
<div class="video-grid">
    <div class="video">
        <video src="videos/onepiece.mp4" type="video/mp4" alt="unable to play the video" controls></video>
    </div>
    <div class="details">
        <h1>One Piece</h1>
        <p>"One Piece" is a popular Japanese anime and manga series created by Eiichiro Oda. It follows the adventures of Monkey D. Luffy and his crew, the Straw Hat Pirates, as they search for the ultimate treasure known as the "One Piece" to become the Pirate King.</p>
        <p>The series is known for its rich world-building, diverse characters, epic battles, and themes of friendship, freedom, and the pursuit of dreams. It has captured the hearts of fans worldwide and has been a long-running success.</p>
        <p>With a compelling storyline and a vast world to explore, "One Piece" has become one of the most beloved and enduring series in the anime and manga industry.</p>
    </div>
</div>

 
