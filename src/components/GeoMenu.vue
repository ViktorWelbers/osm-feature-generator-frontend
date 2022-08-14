<template>
  <a-layout-sider>
    <div class="logo">
      <a-row type="flex" justify="space-around" align="middle">
        <a-col :flex="2.5">
          <img src="@/assets/images/logo.png" alt="NOTHING" width="43"/>
        </a-col>
        <a-col :flex="2.5">
          <a-typography-text style="color: antiquewhite;font-size: 24px">AnGeo</a-typography-text>
        </a-col>
      </a-row>
    </div>
    <a-menu v-model:selectedKeys="selectedKeys" theme="dark" mode="inline">
      <a-menu-item key="1">
        <file-text-filled/>
        <router-link to="/docs"> API Documentation</router-link>
      </a-menu-item>
      <a-menu-item key="2">
        <search-outlined/>
        <router-link to="/"> Try the API</router-link>
      </a-menu-item>
    </a-menu>
  </a-layout-sider>
</template>
<script>

import {SearchOutlined, FileTextFilled} from "@ant-design/icons-vue";
import {defineComponent, ref} from 'vue';

export default defineComponent({
  name: 'GeoMenu',
  components: {
    FileTextFilled,
    SearchOutlined
  },

  setup() {
    return {
      selectedKeys: ref(['4']),
    };
  },
});
</script>

<style>
.logo {
  height: 45px;
  margin: 16px;
}

</style>