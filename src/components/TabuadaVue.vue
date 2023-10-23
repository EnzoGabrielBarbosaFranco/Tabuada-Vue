<template>
  <div>
    <h2>Tabuada em VueJs</h2>
    <div class="input-container">
      <label for="numero">Digite um número:</label>
      <input type="number" id="numero" v-model="numero" @input="atualizarTabuada" />
    </div>
    <table v-if="numero !== null" class="tabuada-table">
      <tr>
        <th>Multiplicador</th>
        <th>Resultado</th>
      </tr>
      <tr v-for="i in 10" :key="i">
        <td>{{ numero }} x {{ i }}</td>
        <td>{{ numero * i }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero: null
    };
  },
  methods: {
    atualizarTabuada() {
      if (this.numero !== null) {
        this.numero = parseInt(this.numero);
      }
    }
  }
};
</script>

<style scoped>
.input-container {
  display: flex;
  flex-direction: column;
  margin-bottom: 20px;
}

label {
  font-size: 18px;
  margin-bottom: 5px;
}

input {
  padding: 10px;
  font-size: 16px;
}

.tabuada-table {
  border-collapse: collapse;
  width: 100%;
}

.tabuada-table th, .tabuada-table td {
  border: 1px solid #ddd;
  padding: 10px;
  text-align: center;
}

.tabuada-table th {
  background-color: #f2f2f2;
  font-weight: bold;
}

.tabuada-table tr:nth-child(even) {
  background-color: #f2f2f2;
}

.tabuada-table tr:nth-child(odd) {
  background-color: #fff;
}
</style>
