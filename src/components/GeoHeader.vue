<template>
  <a-page-header
      style="border: 1px solid rgb(235, 237, 240)"
      title="GeoSh - A geospatial search that let's you explore the world and it's characteristics"
  />
</template>

<script>
const routes = [
  {
    path: '/',
    breadcrumbName: 'Geo-Search'
  },
  {
    path: 'second',
    breadcrumbName: 'Do a Search',
  },
];

export default {
  name: "GeoHeader",
  setup() {
    return {
      routes,
    };
  },
}


</script>

<style scoped>

</style>