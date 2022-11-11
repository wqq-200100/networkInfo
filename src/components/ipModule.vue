<template>
  <div class="system-title">IP信息</div>
  <div class="ipMeg">
    <div>
      <div class="play" v-for="item in props.ipDate">
        <div class="sumIP">
          <div class="chart">
            <img :src="item.url" alt="">
            <div class="ipName">{{ item.name }}</div>
          </div>
          <div class="ipNum">{{ item.num }} <span>个</span></div>
        </div>
      </div>
    </div>
    <div class="ipCharts">
      <bing :dataList="props.dataList" :bgColor=props.bgColor style="width: 200px;height: 150px;"/>
    </div>
  </div>
</template>

<script setup>
import zongbu from "../assets/image/zongbu.png";
import ip from "../assets/image/IP.png";
import duigou from "../assets/image/duigou.png";
import bing from "../charts/bing.vue";

const props = defineProps({
  ipDate:[],
  dataList:[],
  bgColor:[]
})

</script>

<style scoped lang="scss">
.ipMeg {
  width: 100%;
  height: 145px;
  display: flex;
  justify-content: space-between;

  .sumIP {
    width: 100%;
    height: 40px;
    background: rgb(27 53 74);
    display: flex;
    justify-content: space-between;
    border-radius: 8px;
    align-items: center;
    line-height: 50px;
    font-size: 13px;
    margin-bottom: 5px;
    margin-left: 10px;


    .chart {
      display: flex;
      align-items: center;

      img {
        width: 20px;
        height: 20px;
      }

      .ipName {
        margin-left: 5px;
        color: #fff;
      }
    }

    .ipNum {
      font-size: 16px;
      color: yellow;
      margin-right: 4px;

      span {
        color: #999;
        margin-left: 10px;
      }
    }

  }

  .ipCharts {
    width: 40%;
    height: 150px;
    margin-right: 54px;
    margin-top: -20px;
  }
}
</style>
