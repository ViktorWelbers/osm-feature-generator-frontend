<template>
  <div style="background: #ececec; padding: 30px">
    <a-card title="API Documentation" bordered style="width: 85vw">
      <a-card title="General Information" class="inner-card">
        <p>
          This is an API that allows you to search for geospatial features in a radius around a lat lon combination.
          The itself API is built on POSTGIS and OpenStreetMap and was implemented in Go.
        </p>
      </a-card>
      <a-card title="API Patterns" class="inner-card">
        <p></p>
      </a-card>
    </a-card>
    <a-divider></a-divider>
  </div>
</template>

<script>
import {defineComponent} from 'vue';

export default defineComponent({
  name: 'ProfileView',
  setup() {
    return {
      form: {
        name: 'Viktor Welbers',
        email: 'default.mail@gmail.com',
        password: '',
        confirmPassword: '',
        phone: '',
        address: '',
        city: '',
        state: '',
        zip: '',
        country: '',
        website: '',
      },
    };
  },
});
</script>

<style scoped>
.inner-card {
  width: 50%;
  margin-top: 16px;
}
</style>