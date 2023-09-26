<template>
  <q-table
    class="q-pa-md"
    title="Productos"
    no-data-label="Sin productos"
    :columns="columns"
    :rows="productos"
  />
</template>

<script>
const columns = [
  {
    name: "producto",
    label: "Producto",
    align: "left",
    field: "producto",
    sortable: true,
  },
  {
    name: "prioridad",
    label: "Prioridad",
    align: "left",
    field: "prioridad",
    sortable: true,
  },
];
const rows = [
  {
    producto: "producto1",
    prioridad: "Max",
  },
];
export default {
  props: {
    productos: Array,
  },
  setup() {
    return {
      columns,
      rows,
    };
  },
};
</script>
