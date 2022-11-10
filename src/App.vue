<template>
  <div class="box">
    <div class="header">
      <div class="goHome">
        <div><img src="./assets/image/home.png" alt=""></div>
        <div>返回首页</div>
      </div>
      <div class="header-title">网络信息概览</div>
      <div class="time">
        <div><img src="./assets/image/miaobiao.png" alt=""></div>
        <div>2022/11/11</div>
      </div>
    </div>
    <div class="main">
      <div class="main-left">
        <div class="label-title">互联网</div>
        <div class="system-title">网络状态</div>
        <div style="width: 100%;height: 110px;background: #f5a89f"></div>

        <ipModule/>

        <kbModule/>

        <div class="system-title">备案域名</div>
        <div style="width: 100%;height: 145px;background: #f5a89f">
          <el-table :data="tableData" style="width: 100%;height: 100%;">
            <el-table-column fixed prop="date" label="部门" width="125x"/>
            <el-table-column prop="name" label="上云系统" width="80px" />
            <el-table-column prop="state" label="域名" width="130" />
          </el-table>
        </div>
      </div>

      <div class="main-center">
        <div class="yun" style="width: 1000px;height: 500px;background: #f5a89f"></div>
        <div class="yun" style="width: 1000px;height: 370px;background: #ec6f60"></div>
      </div>
      <div class="main-right">
        <div class="label-title">政务外网</div>
        <div class="system-title">网络状态</div>
        <div style="width: 100%;height: 110px;background: #f5a89f"></div>
        <div class="system-title">IP信息</div>
        <div style="width: 100%;height: 145px;background: #f5a89f"></div>
        <div class="system-title">实时速率（kb/s）</div>
        <div style="width: 100%;height: 145px;background: #f5a89f"></div>
        <div class="system-title">累计流量</div>
        <div style="width: 100%;height: 145px;background: #f5a89f"></div>
        <div class="label-title">专线接入</div>
        <div style="width: 100%;height: 145px;background: #f5a89f"></div>
      </div>
    </div>
  </div>
</template>
<script setup>
import ipModule from "./components/ipModule.vue";
import kbModule from "./components/kbModule.vue";

const tableData = [
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
  },
]

</script>

<style scoped lang="scss">
.box {
  height: 100vh;
  display: flex;
  flex-direction: column;

  .header {
    flex: 1;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border: 1px solid palegreen;

    .header-title {
      color: #fff;
      font-size: 35px;
    }

    .goHome, .time {
      display: flex;
      align-items: center;
      margin: 0 20px;
      color: rgb(54, 174, 222);

      img {
        width: 30px;
        height: 30px;
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
      width: 330px;
      height: 96%;
      margin: 0 10px;
      border: 1px solid palegreen;
    }
  }


  ::v-deep(.el-table--enable-row-transition .el-table__body td.el-table__cell){
    background: rgb(10,47,71);
    color: #999;
  }
  ::v-deep(.el-table:not(.el-table--border) .el-table__cell ){
    background: rgb(6, 39, 59);
    color: #2580e5;
  }

  ::v-deep(.el-table__header-wrapper){
    background: rgb(5,30,45);
  }
  ::v-deep(.el-scrollbar){
    background: rgb(10,47,71);
  }

}
</style>
