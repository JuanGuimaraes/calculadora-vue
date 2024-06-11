<script>

export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'soma',
      resultado: 0
    };
  },
  methods: {
    calcular() {
      switch (this.operacao) {
        case 'soma':
          this.resultado = parseFloat(this.numero1) + parseFloat(this.numero2);
          break;
        case 'subtracao':
          this.resultado = parseFloat(this.numero1) - parseFloat(this.numero2);
          break;
        case 'multiplicacao':
          this.resultado = parseFloat(this.numero1) * parseFloat(this.numero2);
          break;
        case 'divisao':
          this.resultado = parseFloat(this.numero1) / parseFloat(this.numero2);
          break;
      }
    }
  }
};
</script>

<template>
  <div class="container">
    <div class="campos">
      <input class="inputs" type="number" v-model="numero1" @input="calcular">
        <select class="seletor" v-model="operacao" @change="calcular">
          <option value="soma">+</option>
          <option value="subtracao">-</option>
          <option value="multiplicacao">*</option>
          <option value="divisao">/</option>
        </select>
      <input class="inputs" type="number" v-model="numero2" @input="calcular">
    <div>Resultado: {{ resultado }}</div>
    </div>
  </div>
</template>

<style scoped>
*{
  margin: 0;
  padding: 0;
  font-family: sans-serif;
}
.container {
  background-color:rgba(199, 236, 238,1.0) ;
  width: 100%;
  height: 100%;
}

.campos {
  margin: 50px auto;
  text-align: center;

}
.inputs, .seletor {
  margin: 10px;
  padding: 4px;
}
</style>
