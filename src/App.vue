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
          <a-row>
            <a-col :span="8">
              <geo-description/>
            </a-col>
            <a-col :span="8">
              <geo-form @ADD-GEO-ITEM-EVENT="addGeoItem" :button-loading="buttonLoading"></geo-form>
            </a-col>
            <a-col :span="8">
              <geo-road-map></geo-road-map>
            </a-col>
            <a-divider/>
            <ul v-for="item in GeoItems" :key="item.id">
              <geo-item v-bind:geo_information="item.label" v-bind:id="item.id"></geo-item>
            </ul>
          </a-row>
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
import GeoDescription from "@/components/GeoDescription";
import GeoRoadMap from "@/components/GeoRoadMap";

export default defineComponent({
  name: 'app',
  components: {
    GeoDescription,
    GeoItem,
    GeoForm,
    GeoMenu,
    GeoHeader,
    GeoRoadMap,
  },

  data() {
    return {
      GeoItems: [],
      info: null,
      buttonLoading: false,
    };
  },

  methods: {
    async addGeoItem(Latitude, Longitude, Radius) {
      this.buttonLoading = true
      const url = 'simple/' + Longitude + '/' + Latitude + '/' + Radius;
      this.info = await (await fetch(url)).json();
      this.buttonLoading = false
      this.GeoItems.push({
        id: uniqueId('geo-'),
        label: this.info
      });
    }
  }
});
</script>

