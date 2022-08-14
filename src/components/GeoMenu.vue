<template>
  <div class="logo"/>
  <a-menu v-model:selectedKeys="selectedKeys" theme="dark" mode="inline">
    <a-menu-item key="2">
      <user-outlined/>
      <router-link to="/profile"> Profile</router-link>
    </a-menu-item>
    <a-menu-item key="3">
      <search-outlined/>
      <router-link to="/"> Geo Feature Search</router-link>
    </a-menu-item>
  </a-menu>
</template>
<script>

import {SearchOutlined, UserOutlined} from "@ant-design/icons-vue";
import {defineComponent, ref} from 'vue';

export default defineComponent({
  name: 'GeoMenu',
  components: {
    // FileImageFilled,
    // UploadOutlined,
    UserOutlined,
    SearchOutlined
  },

  setup() {
    return {
      selectedKeys: ref(['4']),
    };
  },
});


</script>