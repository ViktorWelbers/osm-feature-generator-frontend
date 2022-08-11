<template>
  <a-form :label-col="labelCol" :wrapper-col="wrapperCol">
    <a-form-item label="Latitude">
      <a-input-number v-model:value="lat" placeholder="Latitude"/>
    </a-form-item>
    <a-form-item label="Longitude">
      <a-input-number v-model:value="lon" placeholder="Longitude"/>
    </a-form-item>
    <a-form-item label="Radius">
      <a-input-number v-model:value="radius" placeholder="Radius"/>
    </a-form-item>
    <a-form-item>
      <a-button type="primary" style="margin-left: 50px" @click.prevent="onSubmission">Submit</a-button>
    </a-form-item>
  </a-form>
</template>

<script>
export default {
  methods: {
    onSubmission() {
      if (this.radius === '' || this.lat === '' || this.lon === '') {
        return;
      }
      this.$emit('ADD-GEO-ITEM-EVENT', this.lat, this.lon, this.radius);
      this.lat = '';
      this.lon = '';
      this.radius = '';
    }
  },
  data() {
    return {
      lat: '',
      lon: '',
      radius: ''
    }
  },
  setup() {
    return {
      labelCol: {
        span: 1
      },
      wrapperCol: {
        span: 1
      }
    }
  }
}
</script>

<style scoped>

</style>