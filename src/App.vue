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
          <router-view></router-view>
        </div>
      </a-layout-content>
      <a-layout-footer style="text-align: center">
        Geo-Search ©2022
      </a-layout-footer>
    </a-layout>
  </a-layout>
</template>

<script>
import GeoMenu from "@/components/GeoMenu";
import {defineComponent} from 'vue';
import GeoHeader from "@/components/GeoHeader";

export default defineComponent({
  name: 'app',
  components: {
    GeoMenu,
    GeoHeader,
  }
});
</script>

