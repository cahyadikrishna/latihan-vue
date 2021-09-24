<template>
  <Title title="Catatan Pengeluaran" />
  <FormPengeluaran @entri-pengeluaran="entriPengeluaran($event)"/>
  <ListPengeluaran v-if="showList" :dataPengeluaran="dataPengeluaran"/>
  <h2>Total pengeluaran: {{ totalPengeluaran }}</h2>
  <h4 v-if="warning" class="warning">Ket: Pengeluaran anda terlalu banyak</h4> 
</template>
  
<script>
import Title from './components/Title.vue';
import ListPengeluaran from './components/ListPengeluaran.vue';
import FormPengeluaran from './components/FormPengeluaran.vue';

export default {
  name: 'App',
  components: {
    Title,
    ListPengeluaran,
    FormPengeluaran,
  },
  data(){ 
    return{
      dataPengeluaran : [
        // { nominal: 20000, keterangan: "Makan siang"},
        // { nominal: 25000, keterangan: "Beli pulsa"},
        // { nominal: 15000, keterangan: "Beli bensin"},
      ],
      warning : false
    }
  },
  methods:{
    entriPengeluaran(event){
      this.dataPengeluaran.push(event);
    }
  },
  computed:{
    showList: function(){
      return this.dataPengeluaran.length>0;
    },
    totalPengeluaran: function(){
      // return this.dataPengeluaran.length
      return this.dataPengeluaran.reduce((accum, item) => accum + parseInt(item.nominal), 0);
    }
  },
  watch:{
    totalPengeluaran: function(val){
      if(val>100000){
        this.warning = true
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.warning{
  color: red;
}
</style>
