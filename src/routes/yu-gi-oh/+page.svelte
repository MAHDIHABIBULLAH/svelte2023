<script>
  import { onMount } from 'svelte';

  let cardData = [];
  let showCards = false;
  let selectedFilter = "all"; // Default to show all cards

  async function fetchCardData(filterType = "all") {
    try {
      let url = 'https://db.ygoprodeck.com/api/v7/cardinfo.php';

      // If the filter is set to "Spell Cards," update the URL to fetch spell cards
      if (filterType === "Spell") {
        url = 'https://db.ygoprodeck.com/api/v7/cardinfo.php?type=spell%20card&race=equip';
      }

      const response = await fetch(url);
      const result = await response.json();
      cardData = result.data.slice(0, 20);
    } catch (error) {
      console.error('Error fetching card data:', error);
    }
  }

  onMount(() => {
    fetchCardData(selectedFilter);
  });

  function toggleShowCards() {
    selectedFilter = "all"; // Reset the filter
    showCards = !showCards;
    fetchCardData(selectedFilter);
  }

  // Computed property for filtered cards
  $: filteredCards = cardData.filter((card) => {
    if (selectedFilter === "all") {
      return true; // Show all cards
    } else {
      return card.type === selectedFilter;
    }
  });
</script>

<div class="video-grid">
  <div class="video">
    <video src="videos/yugi.mp4" type="video/mp4" alt="unable to play the video" controls></video>
  </div>
  <div class="details">
    <h1>Yu-Gi-Oh</h1>
    <p>Yu-Gi-Oh! (Japanese: 遊☆戯☆王, Hepburn: Yū-Gi-Ō!, lit. "Game King") is a Japanese manga series written and illustrated by Kazuki Takahashi. It was serialized in Shueisha's Weekly Shōnen Jump magazine between September 1996 and March 2004. The plot follows the story of a boy named Yugi Mutou, who solves the ancient Millennium Puzzle. Yugi awakens a gambling alter-ego or spirit within his body that solves his conflicts using various games.

      The manga series has spawned a media franchise that includes multiple spin-off manga and anime series, a trading card game, and numerous video games. Most of these incarnations involve the fictional trading card game known as Duel Monsters, where each player uses cards to "duel" each other in a mock battle of fantasy "monsters," forming the basis for the real-life Yu-Gi-Oh! Trading Card Game tie-in. The manga was adapted into two anime series; the first anime adaptation was produced by Toei Animation, which aired from April to October 1998, while the second, produced by NAS and animated by Studio Gallop titled Yu-Gi-Oh! Duel Monsters, aired between April 2000 and September 2004. Yu-Gi-Oh! has since become one of the highest-grossing media franchises of all time.
    </p>
    <button on:click={toggleShowCards}>
      {#if showCards}
        Hide Cards
      {:else}
        Show Cards
      {/if}
    </button>

    <!-- Filter dropdown for card types -->
    <select bind:value={selectedFilter}>
      <option value="all">All Cards</option>
      <option value="Spell">Spell Cards</option>
      <option value="Monster">Monster Cards</option>
      <!-- Add more filter options as needed -->
    </select>
  </div>
</div>

{#if showCards}
  <ul class="card-grid">
    {#each filteredCards as card (card.id)}
      <li class="card">
        <img src={`https://images.ygoprodeck.com/images/cards/${card.id}.jpg`} alt={card.name} />
        <p>{card.name}</p>
      </li>
    {/each}
  </ul>
{/if}

