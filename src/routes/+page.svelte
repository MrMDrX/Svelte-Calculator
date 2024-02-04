<script>
  const numbers = ["1", "2", "3", "4", "5", "6", "7", "8", "9", "0", "."];
  const operations = ["/", "x", "-", "+", "="];
  let selectedOp = "";
  let display = "";
  let num1 = "";
  let num2 = "";
  let isDispRes = false;

  function handleOpClick(op) {
    if (!num1) return;
    if (op === "=") {
      if (!num2) return;

      const nbr1 = parseFloat(num1);
      const nbr2 = parseFloat(num2);

      let results = "";

      switch (selectedOp) {
        case "+":
          results = (nbr1 + nbr2).toFixed(2);
          break;
        case "-":
          results = (nbr1 - nbr2).toFixed(2);
          break;
        case "x":
          results = (nbr1 * nbr2).toFixed(2);
          break;
        case "/":
          results = (nbr1 / nbr2).toFixed(2);
          break;
      }
      display = results;
      isDispRes = true;
    }
    selectedOp = op;
  }

  function handleNumClick(nbr) {
    if (isDispRes) handleClr();

    if (display === "" && nbr === "0") return;

    if (nbr === "." && display.includes(".")) return;

    if (!selectedOp) {
      if (display === "" && nbr === ".") {
        num1 = "0.";
        return (display = num1);
      }
      num1 = `${num1}${nbr}`;
      return (display = num1);
    } else {
      if (display === "" && nbr === ".") {
        num2 = "0.";
        return (display = num2);
      }
      num2 = `${num2}${nbr}`;
      return (display = num2);
    }
  }

  function handleClr() {
    num1 = "";
    num2 = "";
    selectedOp = "";
    display = "";
    isDispRes = false;
  }
</script>

<main>
  <div class="calculator">
    <div class="results">
      {display}
    </div>
    <div class="digits">
      <div class="numbers">
        <button on:click={handleClr} class="btn btn-xlg"> C </button>
        {#each numbers as nbr (nbr)}
          <button
            on:click={() => handleNumClick(nbr)}
            class={`btn ${nbr === "0" ? "btn-lg" : null}`}>{nbr}</button
          >
        {/each}
      </div>
      <div class="operations">
        {#each operations as op (op)}
          <button
            on:click={() => handleOpClick(op)}
            class={`btn ${op === selectedOp ? "btn-blue" : "btn-orange"}`}
            >{op}</button
          >
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
    background-color: #282a36;
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
  .btn:hover {
    background-color: #007fa2;
  }
  .btn-lg {
    width: 110px;
  }
  .btn-orange {
    background-color: #f6961d;
  }
  .btn-blue {
    background-color: #007fa2;
  }
  .btn-xlg {
    width: 170px;
  }
  .results {
    height: 80px;
    color: white;
    font-size: 50px;
    display: flex;
    flex-direction: row-reverse;
    margin-right: 10px;
  }
</style>
