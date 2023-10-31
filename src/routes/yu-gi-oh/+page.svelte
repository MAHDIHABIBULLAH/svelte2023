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
  onMount(fetchCardData);
  </script>
  {#if cardData.length > 0}
  <ul class="card-grid">
    {#each cardData as card (card.id)}
      <li class="card">
        <img src={`https://images.ygoprodeck.com/images/cards/${card.id}.jpg`} alt={card.name} />
        <p>{card.name}</p>
      </li>
    {/each}
  </ul>
{:else}
  <p>No card data available.</p>
{/if}