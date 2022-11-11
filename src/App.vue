<template>
  <div class="box">
    <div class="header">
      <div class="header-title">网络信息概览</div>
    </div>

    <div class="main">
      <div class="main-left">

        <div class="label-title">互联网</div>
        <div class="system-title">网络状态</div>
        <div class="image">
          <img class="aa" src="./assets/image/leida.png" alt="">
          <div class="dun">
            <img src="./assets/image/dun.png" alt="">
          </div>
          <div class="text" style="color: red">优</div>
        </div>
        
        <IpModule :ipDate="ipDate" :dataList="dataList" :bgColor="bg"/>

        <KbModule :data="data1"/>

        <NameModule :tableData="tableData1" :myLabel="myLabel1"/>
      </div>

      <div class="main-center">
        <RingModule/>
      </div>

      <div class="main-right">
        <div class="label-title">政务外网</div>
        <div class="system-title">网络状态</div>
        <div class="image">
          <img class="aa" src="./assets/image/leida.png" alt="">
          <div class="dun">
            <img src="./assets/image/dun.png" alt="">
          </div>
          <div class="text" style="color: red">优</div>
        </div>

        <IpModule :ipDate="ipDateRight" :dataList="dataListRight" :bgColor="bgRight"/>

        <KbModule :data="data2"/>

        <NameModule :tableData="tableData2" :myLabel="myLabel2"/>
      </div>
    </div>
  </div>
</template>
<script setup>
import IpModule from "./components/ipModule.vue";
import KbModule from "./components/kbModule.vue";
import NameModule from "./components/nameModule.vue";
import RingModule from "./components/RingModule.vue";
import zongbu from "./assets/image/zongbu.png";
import ip from "./assets/image/IP.png";
import duigou from "./assets/image/duigou.png";


const ipDate = $ref([
  {url: zongbu, name: '总IP', num: 1239},
  {url: ip, name: '分配IP', num: 8867},
  {url: duigou, name: '使用IP', num: 335},
])

const ipDateRight = $ref([
  {url: zongbu, name: '总IP', num: 225},
  {url: ip, name: '分配IP', num: 124},
  {url: duigou, name: '使用IP', num: 1341},
])
const bg = $ref(['#4D88FE', '#50CCCB', '#FFBF3C'])


const dataList = $ref([
  {value: 1048, name: '联通'},
  {value: 735, name: '电信'},
  {value: 580, name: '移动'},
])
const dataListRight = $ref([
  {value: 1048, name: '使用'},
  {value: 735, name: '分配'},
]);
const bgRight = $ref(['#eff53d', '#da3c1f'])

const data1 = $ref({data1: [20000, 20000, 60000], data2: [56300, 64040, 70000]})
const data2 = $ref({data1: [50000, 80000, 90000], data2: [30000, 40000, 70000]})

const tableData1 = [
  {
    date: '哥斯拉美羊羊我',
    name: '新华三云',
    state: '172.221.168.90'
  },
  {
    date: '哥斯拉美羊羊我',
    name: '新华三云',
    state: '172.221.168.90'
  },
  {
    date: '哥斯拉美羊羊我',
    name: '新华三云',
    state: '172.221.168.90'
  },
  {
    date: '哥斯拉美羊羊我',
    name: '新华三云',
    state: '172.221.168.90'
  }, {
    date: '哥斯拉美羊羊我',
    name: '新华三云',
    state: '172.221.168.90'
  }, {
    date: '哥斯拉美羊羊我',
    name: '新华三云',
    state: '172.221.168.90'
  },
]
const myLabel1 = $ref({name: '部门', system: '上云系统', ip: '域名'})

const tableData2 = []
const myLabel2 = $ref({name: '部门', system: '上云系统', ip: 'ip'})


</script>

<style scoped lang="scss">
.box {
  height: 100%;
  display: flex;
  flex-direction: column;

  .header {
    flex: 1;
    width: 100%;
    border: 1px solid palegreen;

    .header-title {
      height: 69px;
      line-height: 69px;
      color: #fff;
      font-size: 35px;
      text-align: center;
    }
  }
}

.main {
  flex: 14;
  width: 100%;
  height: 94%;
  border: 1px solid palegreen;
  display: flex;
  justify-content: space-between;

  .main-right, .main-left {
    width: 430px;
    height: 96%;
    margin: 0 10px;
    border: 1px solid palegreen;

    .image {
      text-align: center;
      position: relative;

      .dun{
        img{
          width: 60px;
          position: absolute;
          top: 50%;
          left: 50%;
          transform: translate(-50%,-50%);
        }
      }
      .text{
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
        font-weight: bold;
      }
    }

    @-webkit-keyframes rotation {
      from {
        -webkit-transform: rotate(0deg);
      }
      to {
        -webkit-transform: rotate(360deg);
      }
    }

    .aa {
      -webkit-transform: rotate(360deg);
      animation: rotation 3s linear infinite;
      -moz-animation: rotation 3s linear infinite;
      -webkit-animation: rotation 3s linear infinite;
      -o-animation: rotation 3s linear infinite;
    }

    img {
      width: 125px;
      border-radius: 50%;
    }
  }
}
</style>
