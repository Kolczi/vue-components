<template>
  <table class="table">
    <thead>
      <tr>
        <th v-for="(column, index) in columns" :key="index">{{ column }}</th>
      </tr>
    </thead>
    <tbody>
      <tr
        v-for="(row, rowIndex) in rows"
        :key="rowIndex"
        @click="onRowClick(row)"
        class="clickable-row"
      >
        <td v-for="(column, columnIndex) in columns" :key="columnIndex">
          {{ row[column] }}
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
/* eslint-disable */
export default {
  props: {
    columns: {
      type: Array,
      required: true,
    },
    rows: {
      type: Array,
      required: true,
    },
  },
  methods: {
    onRowClick(row) {
      alert(row["Email"]);
    },
  },
};
</script>

<style>
.table {
  margin-top: 8px;
  border-collapse: collapse;
  width: 100%;
  margin-bottom: 1rem;
  background-color: #fff;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
  overflow: hidden;
}

.table th,
.table td {
  padding: 0.75rem;
  vertical-align: top;
  border: 1px solid #dee2e6;
}

.table thead th {
  vertical-align: bottom;
  background-color: #f2f2f2;
  font-weight: 600;
  color: #333;
}

.table tbody tr:nth-child(even) {
  background-color: #f8f8f8;
}

.table tbody td {
  text-align: left;
  font-size: 14px;
  color: #555;
}

.table tbody td:first-child {
  font-weight: 600;
}

.clickable-row:hover {
  cursor: pointer;
  background-color: #c9c9c9 !important;
}
</style>
