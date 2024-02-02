<main>
  <div class="calculator">
    <div class="results"></div>
    <div class="digits">
      <div class="numbers">
        <button class="btn btn-xlg"> C </button>
        <button class="btn"> 1 </button>
        <button class="btn"> 2 </button>
        <button class="btn"> 3 </button>
        <button class="btn"> 4 </button>
        <button class="btn"> 5 </button>
        <button class="btn"> 6 </button>
        <button class="btn"> 7 </button>
        <button class="btn"> 8 </button>
        <button class="btn"> 9 </button>
        <button class="btn btn-lg"> 0 </button>
        <button class="btn"> . </button>
      </div>
      <div class="operations">
        <button class="btn btn-orange"> / </button>
        <button class="btn btn-orange"> x </button>
        <button class="btn btn-orange"> + </button>
        <button class="btn btn-orange"> - </button>
        <button class="btn btn-orange"> = </button>
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
