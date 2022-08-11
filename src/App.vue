<template>
  <a-layout>
    <a-layout-sider>
      <geo-menu/>
    </a-layout-sider>
    <a-layout>
      <a-layout-header :style="{ background: '#fff', padding: 0,margin: '20px 16px'}">
        <geo-header/>
      </a-layout-header>
      <a-layout-content :style="{ margin: '24px 16px 0' }">
        <div :style="{ padding: '24px', background: '#fff', minHeight: '100vh' }">
          <geo-form @ADD-GEO-ITEM-EVENT="addGeoItem"></geo-form>
          <ul v-for="item in GeoItems" :key="item.id">
            <geo-item v-bind:geo_information="item.label" v-bind:id="item.id"></geo-item>
          </ul>
        </div>
      </a-layout-content>
      <a-layout-footer style="text-align: center">
        Geo-Search ©2022
      </a-layout-footer>
    </a-layout>
  </a-layout>
</template>

<script>
import GeoItem from './components/GeoItem.vue';
import uniqueId from 'lodash.uniqueid'
import GeoForm from './components/GeoForm';
import GeoMenu from "@/components/GeoMenu";
import {defineComponent} from 'vue';
import GeoHeader from "@/components/GeoHeader";

export default defineComponent({
  name: 'app',
  components: {
    GeoItem,
    GeoForm,
    GeoMenu,
    GeoHeader
  },

  data() {
    return {
      GeoItems: []
    };
  },

  methods: {
    addGeoItem(Latitude, Longitude, Radius) {
      this.GeoItems.push({
        id: uniqueId('geo-'),
        label: ' LAT: ' + Latitude + ' LON: ' + Longitude + ' RADIUS: ' + Radius
      });
    }
  }
});
</script>

