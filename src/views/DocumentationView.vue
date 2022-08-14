<template>
  <div style="background: #ececec; padding: 30px">
    <a-card title="API Documentation" bordered style="width: 85vw">
      <a-card title="General Information" class="inner-card">
        <span>
          The underlying API allows you to search for geospatial features in a radius around a lat lon combination.
          The itself API is built on POSTGIS and OpenStreetMap and was implemented in Go.
        </span>
      </a-card>
      <a-card title="API Patterns" class="inner-card">
          <h1>All Features</h1>
          To get an aggregated feature vector, with a key-value pair for every feature (even if that feature isn't present in the queried radius), the following GET-Request can be used:
          <br><br>
          GET /all/{LONGITUDE}/{LATITUDE}/{RADIUS}
          <br><br>
          <h1>Only collected Features</h1>
          To get an an aggregated feature vector, that just shows a key-value pair for each feature that is present in the queried
          radius, the following GET-Request can be used:
          <br><br>
          GET /simple/{LONGITUDE}/{LATITUDE}/{RADIUS}
          <br><br>
         <h1> Retrieve Data as Slice of Maps</h1>
          To get a slice of maps, instead of a map as previously described following two GET-Requests can be used:
          <br><br>
          For a slice with only collected features:
          <br><br>
          GET /slices/simple/{LONGITUDE}/{LATITUDE}/{RADIUS}
          <br><br>
          For a slice with all features:
          <br><br>
          GET /slices/all/{LONGITUDE}/{LATITUDE}/{RADIUS}
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