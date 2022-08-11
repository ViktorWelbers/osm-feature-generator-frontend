<template>
  <div>
    <label v-bind:for=id>{{ geo_information }}</label>
  </div>
</template>

<script>
export default {
  name: 'GeoItem.vue',
  props: {
    id: {required: true, type: String},
    geo_information: {required: true, type: String}
  }
}
</script>

<style scoped>

</style>