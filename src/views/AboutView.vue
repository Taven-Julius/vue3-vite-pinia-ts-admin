<template>
  <div class="about">
    <h1>This is an about page</h1>
    {{ store.doubleCount }}
    <el-button @click="handleClick">点我</el-button>
  </div>
</template>

<script lang="ts" setup>
import { useCounterStore } from '@/stores/counter'
const store = useCounterStore()

const handleClick = () => {
  store.increment()
}
</script>

<style lang="scss">
.about {
  min-height: calc(100vh - 100px);
  display: flex;
  align-items: center;
}
</style>
