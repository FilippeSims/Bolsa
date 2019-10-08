<template>
  <q-page class="flex flex-center">

    <ul id="teste">
      <li v-for="date in list" :key="date">
        {{date}}
      </li>
    </ul>

  </q-page>
</template>

<script>
import axios from 'axios'
export default {
  name: 'PageIndex',
  data () {
    return {
      list: []
    }
  },


  mounted(){
    axios.get('https://filippesims.com.br/api/')
    .then((res) => {
      this.list = res.data
    })
  }




}


</script>