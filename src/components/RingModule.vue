<template>
  <div class="yun" style="width: 1000px;height: 500px;"></div>
  <div class="yun" style="width: 1000px;height: 370px;">
    <div class="label-title">网环信息</div>
    <div class="system-title">流量日峰值</div>
    <zhexian style="height:40%;width: 100%;" :color="color1" :bg="bg1" :time="time1" :data='zhexiandata'/>
    <div class="system-title">流量日均值</div>
    <zhexian style="height:40%;width: 100%;" :color="color2" :bg="bg2" :time="time1" :data='zhexiandata2'/>
  </div>
</template>

<script setup>
import zhexian from "../charts/zhexian.vue";

const color1 = $ref(['#39a0e4', '#12e5f9'])
const bg1 = $ref({bg1: '#39a0e4', bg2: '#12e5f9'})
const time1 = $ref(['2020/9/23', '2020/9/25', '2020/10/23', '2020/9/23', '2020/9/25', '2020/10/23', '2020/9/23', '2020/9/25', '2020/10/23', '2020/10/23'])
const zhexiandata = $ref({
  data1: [50000, 80000, 90000, 50000, 80000, 90000, 50000, 80000, 90000, 70000],
  data2: [30000, 40000, 70000, 30000, 40000, 70000, 30000, 40000, 70000, 50000]
})

const color2 = $ref(['#4c69d5', '#12e5f9'])
const bg2 = $ref({bg1: '#4c69d5', bg2: '#12e5f9'})
const zhexiandata2 = $ref({
  data1: [10000, 80000, 20000, 10000, 10000, 30000, 50000, 80000, 10000, 70000],
})

</script>

<style scoped lang="scss">

</style>
