<template>
    <a-row :gutter="16">
      <a-col :span="8">
        <geo-description/>
      </a-col>
      <a-col :span="8">
        <geo-form @ADD-GEO-ITEM-EVENT="getGeoInformation" :button-loading="buttonLoading"></geo-form>
      </a-col>
      <a-col :span="8">
        <geo-road-map></geo-road-map>
      </a-col>
    </a-row>
    <a-divider/>
    <geo-table :table-data="geoInformationData"></geo-table>
</template>

<script>
import {defineComponent} from 'vue';
import GeoForm from '@/components/SearchViewComponents/GeoForm';
import GeoDescription from "@/components/SearchViewComponents/GeoDescription";
import GeoRoadMap from "@/components/SearchViewComponents/GeoRoadMap";
import GeoTable from "@/components/SearchViewComponents/GeoTable";

export default defineComponent({
  name: 'HomeView',
  components: {
    GeoDescription,
    GeoForm,
    GeoRoadMap,
    GeoTable
  },

  data() {
    return {
      geoInformationData: [],
      buttonLoading: false,
    };
  },
  methods: {
    async getGeoInformation(Latitude, Longitude, Radius) {
      this.buttonLoading = true;
      const url = 'slices/' + Longitude + '/' + Latitude + '/' + Radius;
      this.geoInformationData = await (await fetch(url)).json();
      console.log(this.geoInformationData);
      this.buttonLoading = false;
    },
  },
});
</script>
