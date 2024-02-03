<script>
  const numbers = ["1", "2", "3", "4", "5", "6", "7", "8", "9", "0", "."];
  const operations = ["/", "x", "+", "-", "="];
</script>

<main>
  <div class="calculator">
    <div class="results"></div>
    <div class="digits">
      <div class="numbers">
        <button class="btn btn-xlg"> C </button>
        {#each numbers as nbr (nbr)}
          <button class={`btn ${nbr === "0" ? "btn-lg" : null}`}>{nbr}</button>
        {/each}
      </div>
      <div class="operations">
        {#each operations as op (op)}
          <button class="btn btn-orange">{op}</button>
        {/each}
      </div>
    </div>
  </div>
</main>

<style>
  main {
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .calculator {
    background-color: rgb(28, 28, 28);
    width: 240px;
    padding: 15px;
    border-radius: 7px;
  }
  .digits {
    display: flex;
  }
  .operations {
    display: flex;
    flex-direction: column;
  }
  .numbers {
    display: flex;
    flex-wrap: wrap;
    width: 200px;
  }
  .btn {
    width: 50px;
    height: 50px;
    border-radius: 100px;
    background-color: rgb(114, 113, 113);
    font-size: 20px;
    font-weight: bold;
    color: white;
    margin: 5px;
    border: none;
  }
  .btn-lg {
    width: 110px;
  }
  .btn-orange {
    background-color: orange;
  }
  .btn-silver {
    background-color: silver;
  }
  .btn-xlg {
    width: 170px;
  }
  .results {
    height: 60px;
    color: white;
    font-size: 50px;
    display: flex;
    flex-direction: row-reverse;
    margin-right: 10px;
  }
</style>
