


  <template>     
    <div class="conversor" >
      <h2 class="text">Conversor de Moedas</h2>
      <label for="moedaOrigem">De:</label>
      <select v-model="moedaOrigem" id="moedaOrigem">
        <option v-for="(cotacao, moeda) in cotacoes" :key="moeda" :value="moeda">{{ moeda }}</option>
      </select>
  
      <label for="moedaDestino">Para:</label>
      <select v-model="moedaDestino" id="moedaDestino">
        <option v-for="(cotacao, moeda) in cotacoes" :key="moeda" :value="moeda">{{ moeda }}</option>
      </select>
  
      <input  v-model="valorOrigem" type="number" placeholder="Valor" />
      <button type="button" v-on:click="convert">Converter</button>
      
      <p v-if="valorDestino !== null">Valor em {{ moedaDestino }}: {{ valorDestino }}</p>
    </div>
  </template>
  
  <script>
  /* eslint-disable */
  export default {
    name: 'Conversor',
    data() {
      return {
        moedaOrigem: '',
        moedaDestino: '',
        valorOrigem: '',
        valorDestino: null,
        cotacoes: {
          USD: 1.00, // Dólar americano
          BRL: 5.25, // Real brasileiro
          EUR: 0.85, // Euro
          GBP: 0.75, // Libra esterlina
          JPY: 110.00, // Iene japonês
          AUD: 1.35, // Dólar australiano
          CAD: 1.25, // Dólar canadense
          CHF: 0.91, // Franco suíço
          CNY: 6.45, // Yuan chinês
          INR: 74.50 // Rúpia indiana
        }
      };
    },
    methods: {
      convert() {
        const valorEmDolar = this.valorOrigem / this.cotacoes[this.moedaOrigem];
        this.valorDestino = (valorEmDolar * this.cotacoes[this.moedaDestino]).toFixed(2);
      }
    }
  };





</script>

<style scoped>

.conversor {
  padding: 20px;
  min-width: 100px;
  box-shadow: 0 4px 8px 0 rgba(rgb(0, 0, 0, 0.2));
}

button[type="button"] {
  padding: 10px;
  background-color: #007BFF;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  margin-left: 10px;
}



</style>





















