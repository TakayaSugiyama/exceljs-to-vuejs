<template>
  <div id="app">
    <table id="table-to-sheet">
      <tr>
        <th>Firstname</th>
        <th>Lastname</th>
        <th>Age</th>
      </tr>
      <tr>
        <td>Jill</td>
        <td>Smith</td>
        <td>50</td>
      </tr>
      <tr>
        <td>Eve</td>
        <td>Jackson</td>
        <td>94</td>
      </tr>
    </table>
    <button @click="downloadExcelFile()">エクセルファイルをダウンロード</button>
  </div>
</template>

<script>
import XLSX from 'xlsx'

export default {
  methods: {
    downloadExcelFile: ()=>{
      const data = document.getElementById('table-to-sheet');
      const wb = XLSX.utils.table_to_book(data);
      XLSX.writeFile(wb,'demo.xlsx');
    }
  }
}
</script>
