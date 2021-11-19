<script>
  let current = 0;
  let question = qs[current];
  let qs = [
    "",
    "Are you facing a clean direction (no trailing direction)?",
    "Are you facing facing a northern direction?",
    "Are you facing a westward direction?",
  ];
  let key = 0;
  var solution;
  var directions = ["E", "NE", "N", "NW", "W", "SW", "S", "SE"];
  
  function solved() {
    if (current >= qs.length) {
      solution = directions[key];
      return false;
    } else {
      return true;
    }
  }

</script>

<style>
  .check {
    display: inline-block;
  }
</style>

<main>
  {#if !solved()}
    <h1>{question}</h1>
    <button class="check" on:click={() => {
      key += 1;
      current += 1;
      question = qs[current]
    }}><h2>TRUE</h2></button>
    <button class="check" on:click={() => {
      current += 1;
      question = qs[current]
    }}><h2>FALSE</h2></button>
  {:else}
    <h1>{solution}</h1>
  {/if}
</main>