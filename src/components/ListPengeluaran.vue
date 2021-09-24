<template>
    <table id="catatan">
      <tr>
        <th>Pengeluaran</th>
        <th>Keterangan</th>
      </tr>
      <tr v-for=" (pengeluaran, index) in dataPengeluaran " :key="index">
        <td>{{ pengeluaran.nominal }}</td>
        <td>{{ pengeluaran.keterangan }}</td>
      </tr>
    </table>
</template>

<script>
export default {
  props:{
    dataPengeluaran : Array
    }
}
</script>

<style scoped>
  table{
    border-collapse: collapse;
    width: 100%;
  }

  #catatan td, #catatan th{
    border: 1px solid #ddd;
    padding: 8px;
  }

  #catatan tr:nth-child(even){
    background-color: #ddd;
  }

  #catatan th{
    padding-top: 12px;
    padding-bottom: 12px;
    background-color: #04AA6D;
    color: white;
  }
</style>