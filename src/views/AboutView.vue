<template>
  <div class="about">
    <h1>This is an about page</h1>
    {{ store.doubleCount }}
    <!-- <Footer v-model:count="count"></Footer> -->
    <el-button @click="handleClick">点我</el-button>
  </div>
</template>

<script lang="ts" setup>
import Footer from './Footer.vue'
import { useCounterStore } from '@/stores/counter'
import { ref } from 'vue'
const store = useCounterStore()
const count = ref(navigator.userAgent)
const handleClick = () => {
  console.log('res')
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
