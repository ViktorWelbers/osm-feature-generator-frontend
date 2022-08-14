<template>
  <a-layout-header ></a-layout-header>
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