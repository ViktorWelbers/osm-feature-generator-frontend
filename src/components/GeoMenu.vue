<template>
  <div class="logo"/>
  <a-menu v-model:selectedKeys="selectedKeys" theme="dark" mode="inline">
<!--    <a-menu-item key="1">-->
<!--      <user-outlined/>-->
<!--      <span class="nav-text">Home</span>-->
<!--    </a-menu-item>-->
<!--    <a-menu-item key="2">-->
<!--      <file-image-filled/>-->
<!--      <span class="nav-text">Images</span>-->
<!--    </a-menu-item>-->
<!--    <a-menu-item key="3">-->
<!--      <upload-outlined/>-->
<!--      <span class="nav-text">Last Searches</span>-->
<!--    </a-menu-item>-->
    <a-menu-item key="4">
      <heat-map-outlined/>
      <span class="nav-text">Search a location</span>
    </a-menu-item>
  </a-menu>
</template>
<script>

import {HeatMapOutlined} from "@ant-design/icons-vue";
import {defineComponent, ref} from 'vue';

export default defineComponent({
  name: 'GeoMenu',
  components: {
    // FileImageFilled,
    // UserOutlined,
    // UploadOutlined,
    HeatMapOutlined
  },

  setup() {
    return {
      selectedKeys: ref(['4']),
    };
  },
});


</script>