<template>
  <div class="system-title">实时速率（kb/s）</div>
  <div style="width: 100%;height: 145px;">
    <zhexian :color="color1" :bg="bg1" :time="time1" />
  </div>

  <div class="system-title">累计流量</div>
  <div style="width: 100%;height: 145px;">
    <zhexian :color="color2" :bg="bg2" :time="time2"/>
  </div>
</template>

<script setup>
import {reactive} from "vue";

import zhexian from "../charts/zhexian.vue";
const color1 = $ref(['#f6e30c', '#00D68A'])
const bg1 = $ref({bg1:'#f6e30c', bg2:'#00D68A'})
const color2 = $ref([ '#ec5a2e','#0C65F6'])
const bg2 = $ref({bg1:'#ec5a2e', bg2:'#0C65F6'})
const time1 = $ref(['2020/9/23', '2020/9/25', '2020/10/23'])
const time2 = $ref(['2020/9/23',  '2020/10/23'])

</script>

<style scoped lang="scss">

</style>
