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
              <geo-form @ADD-GEO-ITEM-EVENT="getGeoInformation" :button-loading="buttonLoading"></geo-form>
            </a-col>
            <a-col :span="8">
              <geo-road-map></geo-road-map>
            </a-col>
          </a-row>
          <a-divider/>
          <div v-if="tableData">
            <geo-table> </geo-table>
          </div>
        </div>
      </a-layout-content>
      <a-layout-footer style="text-align: center">
        Geo-Search ©2022
      </a-layout-footer>
    </a-layout>
  </a-layout>
</template>

<script>
import GeoForm from './components/GeoForm';
import GeoMenu from "@/components/GeoMenu";
import {defineComponent} from 'vue';
import GeoHeader from "@/components/GeoHeader";
import GeoDescription from "@/components/GeoDescription";
import GeoRoadMap from "@/components/GeoRoadMap";
import GeoTable from "@/components/GeoTable";

export default defineComponent({
  name: 'app',
  components: {
    GeoDescription,
    GeoForm,
    GeoMenu,
    GeoHeader,
    GeoRoadMap,
    GeoTable
  },

  data() {
    return {
      geoInformationData: null,
      buttonLoading: false,
      tableData: null,
    };
  },
  setup() {
    return {
      columns: [
        {
          title: 'Feature',
          dataIndex: 'feature',
          key: 'feature',
        },
        {
          title: 'Amount',
          dataIndex: 'amount',
          key: 'amount',
        },
      ]
    };
  },
  methods: {
    async getGeoInformation(Latitude, Longitude, Radius) {
      this.buttonLoading = true
      const url = 'simple/' + Longitude + '/' + Latitude + '/' + Radius;
      this.geoInformationData = await (await fetch(url)).json();
      console.log(this.geoInformationData);
      this.buttonLoading = false
      this.createTableDataSource()
    },
    createTableDataSource() {
      this.geoInformationData.forEach((value, key) => {
        this.tableData.push({
          feature: key,
          value: value,
        });
      });
    },
  }
});
</script>

