<template>
  <a-form :label-col="labelCol">
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
      <a-button type="primary" :loading="buttonLoading" style="margin-left: 100px" @click.prevent="onSubmission">
        Search the area!
      </a-button>
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
  props: {
    buttonLoading: {Boolean, default: false},
  },
  data() {
    return {
      lat: '',
      lon: '',
      radius: '',
    }
  },
  setup() {
    return {
      labelCol: {
        span: 4
      }
    }
  }
}
</script>

<style scoped>

</style>