<script setup lang="ts">
import { RouterView } from 'vue-router'
</script>

<template>
  <div class="wrapper">
    <el-container>
      <el-aside width="200px">Aside</el-aside>
      <el-container>
        <el-header>Header</el-header>
        <el-main>
          <RouterView />
        </el-main>
      </el-container>
    </el-container>
  </div>


</template>

<style scoped lang="scss">
  .wrapper {
    min-height: 100vh;
    width: 100%;
    .el-aside {
      background: #f5f5f5;
      text-align: center;
    }
    .el-header {
      background: #c6e2ff;
    }
  }
</style>
