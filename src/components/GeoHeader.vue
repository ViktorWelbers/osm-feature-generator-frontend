<template>
  <a-page-header
      style="border: 1px solid rgb(235, 237, 240)"
      title="Search for a Location"
      :breadcrumb="{ routes }"
  />
</template>

<script>
const routes = [
  {
    path: 'index',
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