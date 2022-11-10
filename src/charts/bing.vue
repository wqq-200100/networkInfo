<template>
<!--饼图-->
  <div ref="myChartRef" ></div>
</template>

<script setup>
import {onMounted} from "vue";
import * as echarts from 'echarts'

let myChart = null
const myChartRef = $ref()
const props =  defineProps({
  dataList:[]
})

const dataList = props.dataList;
const handleData = {};
let sum = 0;
// 求和
dataList.map((item) => {
  sum += item.value;
});
// 数据处理
dataList.map((item) => {
  handleData[item.name] = item;
  handleData[item.name].percentage = ((item.value / sum) * 100).toFixed(1) + '%';
});

const option = {
  legend: {
    show: true,
    icon: 'circle',
    right: '3%',
    left: 'center',
    bottom: '10%',
    itemWidth: 10,
    itemStyle: {
      borderColor: 'none',
    },
    textStyle: {
      color:'#fff',
      rich: {
        name: {
          color: '#606266',
          fontSize: 14,
        },
        percentage: {
          color: '#606266',
          fontSize: 16,
          padding: [0, 0, 0, 30],
          align: 'right',
        },
      },
    },
  },
  tooltip: {
    trigger: 'item',
  },
  series: [
    {
      type: 'pie',
      color: ['#4D88FE', '#50CCCB', '#FFBF3C'],
      radius: '70%',
      left: 'center',
      data: dataList,
      emphasis: {
        itemStyle: {
          shadowBlur: 10,
          shadowOffsetX: 0,
          shadowColor: 'rgba(0, 0, 0, 0.5)',
        },
      },
      labelLine: {
        show: true,
        length: 10,
        length2: 60,
      },
      label: {
        show:false,
        width:100,
        fontSize:12,
      },
      itemStyle: {
        borderColor: '#fff',
      },
    },
  ],
};



onMounted(() => {
  myChart = echarts.init(myChartRef)
  myChart.setOption(option)
})
</script>

<style scoped lang="scss">

</style>
