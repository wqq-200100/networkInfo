<template>
  <div class="system-title">实时速率（kb/s）</div>
  <div style="width: 100%;height: 145px;">
    <zhexian :color="color1" :bg="bg1" :time="time1"  :data=propsKb.data />
  </div>

  <div class="system-title">累计流量</div>
  <div style="width: 100%;height: 145px;">
    <zhexian :color="color2" :bg="bg2" :time="time2" :data=propsKb.data />
  </div>
</template>

<script setup>
import zhexian from "../charts/zhexian.vue";

const propsKb = defineProps({
  data:[]
})
const color1 = $ref(['#f6e30c', '#00D68A'])
const bg1 = $ref({bg1:'#f6e30c', bg2:'#00D68A'})
const time1 = $ref(['2020/9/23', '2020/9/25', '2020/10/23'])

const color2 = $ref([ '#ec5a2e','#0C65F6'])
const bg2 = $ref({bg1:'#ec5a2e', bg2:'#0C65F6'})
const time2 = $ref(['2020/9/23',  '2020/10/23'])



</script>

<style scoped lang="scss">

</style>
