<!--<template>
  <div class="conversor">
    <h2>dolar para Real</h2>
    <input v-model="dolar" type="number" placeholder="Valor em dólares"/>
    <button type="button" v-on:click="convert">Converter</button>
    
    
  </div>
</template>

<script>
 /* eslint-disable */ export default {
  name: 'Conversor',
  data() {
    return {
      dolar: '',
      real: null,
      cotacao: 5.25 
    };
  },
  methods: {
    convert() {
      this.real = (this.dolar * this.cotacao).toFixed(2);
    }
  }
};
<template>
  <div class="conversor">
      <h2>{{ moedaA }} para {{ moedaB }}</h2>
      <input type="text" v-model="moedaA_valor" v-bind:placeholder="moedaA" />
      <input type="button" value="Converter" v-on:click="converter"/>
      <p v-if="moedaA_valor !== null">Valor em reais: R$ {{ moedaB_valor }}</p>
    </div>
  </template>
  
  <script>
  /* eslint-disable */
  export default {
    name: 'Conversor',
    props: ['moedaA', 'moedaB'],
    data() {
      return {
        moedaA_valor: '',
        moedaB_valor: 0
      };
    },
    methods: {
      converter() {
        console.log(this.moedaB_valor)
        const taxaConversao = 5.63;
        this.moedaB_valor = (parseFloat(this.moedaA_valor) * taxaConversao).toFixed(2);
      }
    }
  };-->


  <template>     
    <div class="conversor" >
      <h2>Conversor de Moedas</h2>
      <label for="moedaOrigem">De:</label>
      <select v-model="moedaOrigem" id="moedaOrigem">
        <option v-for="(cotacao, moeda) in cotacoes" :key="moeda" :value="moeda">{{ moeda }}</option>
      </select>
  
      <label for="moedaDestino">Para:</label>
      <select v-model="moedaDestino" id="moedaDestino">
        <option v-for="(cotacao, moeda) in cotacoes" :key="moeda" :value="moeda">{{ moeda }}</option>
      </select>
  
      <input v-model="valorOrigem" type="number" placeholder="Valor" />
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
}

text[type="text"] { 
 margin-top: 40px;
  width: 100%;
  padding: 8px;
  margin-bottom: 10px;
  
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

button[type="button"]:hover {
  background-color: #0056b3;
}
</style>





















