<template>
  <div class="system-title">备案域名</div>
  <div style="width: 100%;height: 244px;background: #f5a89f">
    <el-table :data=tableData.tableData style="width: 100%;height: 100%;">
      <el-table-column prop="date" :label=tableData.myLabel.name width="170px"/>
      <el-table-column prop="name" :label=tableData.myLabel.system width="120px" />
      <el-table-column prop="state" :label=tableData.myLabel.ip width="140px" />
    </el-table>
  </div>
</template>

<script setup>
const tableData =defineProps({
  tableData:[],
  myLabel:{
    name:'',
    system:'',
    ip:''
  }
})

</script>

<style scoped lang="scss">
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

::v-deep(.el-table--enable-row-hover .el-table__body tr:hover>td.el-table__cell){
  background-color: #456ba5;

}
</style>
