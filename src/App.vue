<template>
  <div id="app">
   <div>
    <Perfume :perfumes="perfumes"></Perfume>
   </div>
  </div>
</template>

<script>
import axios from 'axios'
import Perfume from './components/Perfume.vue';
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      perfumes:[]
    }
  },
  created() {
  // Simple GET request using axios
  axios.get("https://gs-euw1-public-data-prod.s3-eu-west-1.amazonaws.com/new-web/test/test.json")
    .then(response => this.perfumes = response.data.hits);
  },
  components:{
    Perfume
  }
}
</script>

<style>
body{
  background:#f5f5f5;
  font-family:sans-serif;
}
</style>
