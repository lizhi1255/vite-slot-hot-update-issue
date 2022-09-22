<script setup lang="ts">
import MyComponent from "../components/MyComponent.vue";
const data = [{
  updateTime: '2022.02.02 22:22:22',
  eventStatus: '未处理'
}]
</script>

<template>
  <main class="main">
    <MyComponent>
      <template #default="scope">
        {{scope.text}}--{{scope.count}}
      </template>
    </MyComponent>
    <el-table :data="data" style="width: 100%">
      <el-table-column prop="updateTime" label="时间" />
      <el-table-column prop="eventStatus" label="事件状态" width="80px">
        <template #default="scope">
          <div class="status" :class="scope.row.eventStatus === '未处理'?'untreated':'processed'">
            <div class="dot"></div>
            <div class="text">{{scope.row.eventStatus}}123</div>
          </div>
        </template>
      </el-table-column>
    </el-table>
  </main>
</template>

<style lang="less" scoped>
.status {
  display: flex;
  align-items: center;

  &.untreated {
    .dot {
      background: #FA5151;
    }

    .text {
      color: #FA5151;
    }
  }

  &.processed {
    .dot {
      background: #1ffb96;
    }

    .text {
      color: #1ffb96;
    }
  }

  .dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    margin-right: 6px;
  }

  .text {
    line-height: 1;
  }
}
</style>
