<script>
  import { calcularArea } from './calculadora.js'; // Importando a função
  import '.style.css';

  let comprimento = 0;
  let largura = 0;
  let area = null;

  // Usando a função importada para calcular a área
  function calcular() {
    area = calcularArea(comprimento, largura);
  }
</script>

<style>
  body {
    margin: 0;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    color: blue;
    font-family: Arial;
  }

  #container {
    font-size: 25px;
    border: 6px solid black;
    padding: 20px;
    border-radius: 14px;
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
  }

  #resultado {
    margin-top: 20px;
  }

  #botao {
    padding: 10px;
    font-size: 20px;
    border: 8px;
    border-radius: 8px;
    background-color: gray;
    margin-top: 18px;
  }

  #botao:hover {
    background-color: greenyellow;
  }

  input {
    font-size: 16px;
    padding: 10px;
    margin: 5px 0;
  }
</style>

<div id="container">
  <h1>Calculadora de Área Quadrada</h1>
  
  <label for="comprimento">Comprimento em (CM):</label>
  <input id="inputComprimento" type="number" bind:value={comprimento} placeholder="Comprimento (CM)" required />

  <label for="largura">Largura em (CM):</label>
  <input id="inputLargura" type="number" bind:value={largura} placeholder="Largura (CM)" required />

  <br />

  <button id="botao" on:click={calcular}>Calcular</button>

  {#if area !== null}
    <div id="resultado">
      <p>Área total em m²: {area.toFixed(2)}</p>
    </div>
  {/if}
</div>
