<template>
  <q-page class="flex flex-center">
    <table>
      <tr>
        <th>Data</th>
        <th>Fechamento</th>
        <th>Volume</th>
      </tr>
      <tr v-for="(cotacao, key) in list" :key="key">
       <td>{{cotacao[0].display}}</td>
       <td>{{cotacao[2]}}</td>
       <td>{{cotacao[6]}}</td>
      </tr>
    </table>
  </q-page>
</template>

<script>
import axios from "axios";
export default {
  name: "PageIndex",
  data() {
    return {
      list: []
    };
  },
  mounted() {
    axios.get("https://filippesims.com.br/api/").then(res => {
      this.list = res.data;
      console.log(teste)
    });
  }
};
</script>

<style scoped>
table {
  border: 2px solid #42b983;
  border-radius: 3px;
  background-color: #fff;
  margin-top: 20px;
}

th {
  background-color: #42b983;
  color: rgba(255,255,255,0.66);
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

td {
  background-color: #f9f9f9;
}

th, td {
  min-width: 120px;
  padding: 10px 20px;
}
</style>