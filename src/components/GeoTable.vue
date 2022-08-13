<template>
  <a-table v-if="tableData.length > 1" :columns="columns" :data-source="tableData" bordered>
    <template #bodyCell="{ column, text }">
      <template v-if="column.dataIndex === 'feature'">
        <a>{{ text }}</a>
      </template>
    </template>
    <template #title>Search Results</template>
  </a-table>
</template>

<script>
import {defineComponent} from 'vue';

const columns = [{
  title: 'Geo-Feature',
  dataIndex: 'feature',
}, {
  title: 'Amount of Feature',
  dataIndex: 'amount',
}];
export default defineComponent({
  name: "GeoTable",
  props: {
    tableData: {type: Array, default: () => []},
    aids: null,
  },
  setup() {
    return {
      columns,
    };
  },
});

</script>

<style scoped>

</style>