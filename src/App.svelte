<script>
  import { calcularArea } from './calculadora.js'; // Importando a função

  let comprimento = 0;
  let largura = 0;
  let area = null;

  // Usando a função importada para calcular a área
  function calcular() {
    area = calcularArea(comprimento, largura);
  }
</script>


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
