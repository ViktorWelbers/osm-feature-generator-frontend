<template>
  <a-card style="font-size: 20px" title="Roadmap for GeoSh">
    <a-timeline>
      <a-timeline-item color="green">
        <template #dot>
          <check-circle-outlined style="font-size: 16px"/>
        </template>
        Create a backend in Go that will return a JSON file with the results of the search
      </a-timeline-item>
      <a-timeline-item color="green">
        <template #dot>
          <check-circle-outlined style="font-size: 16px"/>
        </template>
        Start with the implementation of the frontend in Vue.js
      </a-timeline-item>
      <a-timeline-item color="red">
        <template #dot>
          <clock-circle-outlined style="font-size: 16px"/>
        </template>
        Work on the backend to only show relevant data
      </a-timeline-item>
      <a-timeline-item>Actually make the frontend useful</a-timeline-item>
    </a-timeline>
  </a-card>
</template>

<script>
import {CheckCircleOutlined, ClockCircleOutlined} from "@ant-design/icons-vue";

export default {
  name: "GeoRoadMap",
  components: {
    ClockCircleOutlined,
    CheckCircleOutlined
  },
}
</script>

<style scoped>

</style>