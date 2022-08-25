<script>
export default {
  data() {
    return {
      pessoas: "",
      valor_conta: "",
      gorjeta: "",
      valor_final: "",
    };
  },
  methods: {
    calcular() {
      const pessoas = this.pessoas;
      const valor_conta = this.valor_conta;
      const gorjeta = this.gorjeta;
      let valor_gorjeta = 0;
      let resultado;
      valor_gorjeta = valor_conta * (gorjeta / 100);
      resultado = (valor_conta + valor_gorjeta) / pessoas;
      resultado = Math.round(resultado);
      this.valor_final = resultado.toFixed(2);
    },
  },
};
</script>

<template>
  <div class="principal">
    <label>
      <p>Qual foi o valor da sua conta?</p>
      <input type="number" v-model="valor_conta" id="conta" class="input"/>
    </label>

    <label class="">
      <p>Sua Opinião sobre o serviço prestado?</p>
      <select v-model="gorjeta" class="input">
        <option value="30"> Excepcional</option>
        <option value="25"> Muito bom</option>
        <option value="20"> Bom</option>
        <option value="15"> Ok</option>
        <option value="10"> Ruim</option>
        <option value="5"> Péssimo</option>
      </select>
    </label>

    <label>
      <p>Quantas pessoas estão dividindo a conta?</p>
      <input type="number" v-model="pessoas" id="pessoas" class="input">
    </label>
    <button type="button" @click="calcular">
      Calcular
      <span id="resultado"></span>
    </button>
    <input type="text" class="resposta" v-model="valor_final" disabled />
  </div>
</template>

<style>


.input{
  width: 100%;
  height: 25px;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 0 10px;
  margin-top: 10px;
  font-size: 16px;
}

.principal {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-top: 10px;
  margin-bottom: 10px;
  margin-left: 10px;
  margin-right: 10px;
  padding: 10px;
  border: 1px solid #000;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
}
button {
  background-color: green;
  border: none;
  color: white;
  padding: 10px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  border-radius: 10px;
}
.resposta {
  color: white;
  background-color: green;
  border-radius: 10px;
  width: 70%;
  height: 40px;
  font-size: 20px;
  text-align: center;
  margin-top: 10px;
}
</style>
