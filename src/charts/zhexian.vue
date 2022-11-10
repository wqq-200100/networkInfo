<template>
<!--饼图-->
  <div ref="myChartRef" style="height: 100%;width: 100%;" ></div>
</template>

<script setup>
import {onMounted} from "vue";
import * as echarts from 'echarts'

let myChart = null
const myChartRef = $ref()
const props = defineProps({
  color:[],
  time:[],
  bg:{
    bg1:'',
    bg2:''
  },
})

const option = {
  color: props.color,
  tooltip: {
    confine: true,
  },
  grid: {
    left: '2%',
    right: '4%',
    bottom: '5%',
    top: '30px',
    containLabel: true,
  },
  legend: {
    icon: 'rect',
    orient: 'horizontal',
    left: 'right',
    itemWidth: 12,
    itemHeight: 12,
    formatter: ['{a|{name}}'].join('\n'),
    textStyle: {
      fontSize: 12,
      color: '#6A93B9',
      height: 8,
      rich: {
        a: {
          verticalAlign: 'bottom',
        },
      },
    },
    data: ['上行', '下行'],
  },
  xAxis: {
    type: 'category',
    axisLine: {
      lineStyle: {
        color: 'rgba(255,255,255,0.45)',
      },
    },
    axisLabel: {
      // interval:0,
      fontSize: 12,
      color: '#6A93B9',
    },
    axisTick: {
      show: false,
    },
    data: props.time,
  },
  yAxis: {
    type: 'value',
    min: 0,
    minInterval: 1,
    nameTextStyle: {
      fontSize: 12,
      color: '#BAE7FF',
      align: 'center',
    },
    splitLine: {
      lineStyle: {
        color: 'rgba(255, 255, 255, 0.15)',
        // type: 'dashed', // dotted 虚线
      },
    },
    splitArea: { show: false },
    axisLine: {
      show: false,
    },
    axisTick: {
      show: false,
    },
    axisLabel: {
      fontSize: 12,
      fontFamily: 'Bebas',
      color: '#6A93B9',
    },
  },
  series: [
    {
      type: 'line',
      showSymbol: false, // 数据标点
      smooth: true, // 是否曲线
      name: '上行', // 图例对应类别
      data: [20000, 20000, 60000], // 纵坐标数据
      areaStyle: { // 区域颜色
        color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [{
          offset: 0,
          color: props.bg.bg1,
        }, {
          offset: 1,
          color:'rgba(12, 101, 246, 0.1)',
        }]),
      },
    }, {
      type: 'line',
      smooth: true,
      showSymbol: false,
      name: '下行',
      data: [56300, 64040, 70000],
      areaStyle: {
        color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [{
          offset: 0,
          color: props.bg.bg2,
        }, {
          offset: 1,
          color: 'rgba(0, 214, 138, 0.1)',
        }]),
      }
    }
  ],
};




onMounted(() => {
  myChart = echarts.init(myChartRef)
  myChart.setOption(option)
})
</script>

<style scoped lang="scss">

</style>
