<script>
  let desciption = "";
  $: totalChars = desciption.length;
  $: totalWords = desciption.split(" ").length;

  $: if (desciption.length > 5) {
    console.log("banana");
  }
</script>

<style>

</style>

<div>
  <p>{desciption}</p>
  <textarea
    bind:value={desciption}
    name="description"
    id="description"
    placeholder="Test writing..."
    rows="5" />
  <p>Total Characters: {totalChars}</p>
  <p>Total words: {totalWords}</p>
</div>
