<script>
  import Emoji from "./Emoji.svelte";

  let currentEmoji = "😁";
  const emojis = [
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

  button {
    background-color: darkorange;
    padding: 8px;
    border-radius: 4px;
    border: 2px solid black;
    box-shadow: 6px 6px 0 black;
    margin-top: 10px;
  }

  button:hover {
    box-shadow: 4px 4px 0 black;
    transition: all 0.2s ease 0s;
    background-color: #ff8c00da;
  }
</style>

<main>
  <h1>Randomize Emoji</h1>
  <Emoji {currentEmoji} />
  <button on:click={handleRandomize}>Randomize</button>
</main>
