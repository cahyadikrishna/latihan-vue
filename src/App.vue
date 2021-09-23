<template>
  <Title title="Catatan Pengeluaran" />
  <ListPengeluaran :dataPengeluaran="dataPengeluaran"/>
</template>
  
<script>
import Title from './components/Title.vue';
import ListPengeluaran from './components/ListPengeluaran.vue';

export default {
  name: 'App',
  components: {
    Title,
    ListPengeluaran,
  },
  data(){
    return{
      dataPengeluaran : [
        { nominal: 20000, keterangan: "Makan siang"},
        { nominal: 25000, keterangan: "Beli pulsa"},
        { nominal: 15000, keterangan: "Beli bensin"},
      ]
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
  margin-top: 60px;
}
</style>
