<template>
    <table>
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