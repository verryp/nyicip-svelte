<script>
  import Emoji from "./Emoji.svelte";
  import EmojiDesc from "./EmojiDesc.svelte";
  import EmojiList from "./EmojiList.svelte";

  let isLoading = false;
  let showList = false;
  let currentEmoji = "😁";
  let emojis = [
    "😆",
    "😼",
    "👷",
    "👩‍🚀",
    "🥕",
    "👕",
    "🦆",
    "😇",
    "👋",
    "👴",
    "🐍",
    "🚗"
  ];

  const randomizeEmoji = () =>
    emojis[Math.floor(Math.random() * emojis.length)];

  const handleRandomize = () => (currentEmoji = randomizeEmoji());

  const handleShowList = () => (showList = !showList);

  setTimeout(() => {
    isLoading = true;
  }, 3000);
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    /* border-radius: 4px;
    border: 2px solid #ff7300fd; */
    font-weight: 600;
    text-shadow: 5px 5px 0 #ff9100ee;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }

  .btnRandomize {
    background-color: darkorange;
    padding: 8px;
    border-radius: 4px;
    border: 2px solid black;
    box-shadow: 6px 6px 0 black;
    margin-top: 10px;
  }

  .btnRandomize:hover {
    box-shadow: 4px 4px 0 black;
    transition: all 0.2s ease 0s;
    background-color: #ff8c00da;
  }

  .btnShowList {
    background-color: khaki;
    padding: 8px;
    border-radius: 4px;
    border: 2px solid black;
    box-shadow: 6px 6px 0 black;
    margin-top: 10px;
    margin: 0px 6px 0px 6px;
  }

  .btnShowList:hover {
    box-shadow: 4px 4px 0 black;
    transition: all 0.2s ease 0s;
    background-color: lightgoldenrodyellow;
  }
</style>

<main>
  <h1>Randomize Emoji</h1>
  {#if isLoading}
    <Emoji {currentEmoji} />
    <EmojiDesc />

    <div>
      <button class="btnRandomize" on:click={handleRandomize}>Randomize</button>
      <button class="btnShowList" on:click={handleShowList}>
        {showList ? 'Hidden' : 'Show'} List
      </button>
    </div>
  {:else}
    <h2>Loading ...</h2>
  {/if}

  {#if showList}
    <EmojiList {emojis} />
  {/if}
</main>
