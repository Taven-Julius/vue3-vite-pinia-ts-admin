<template>
    <div>
        <h2>{{ count }}</h2>
        <el-button @click="handleClick">子组件</el-button>
        <el-date-picker v-model="item.date" type="daterange" range-separator="To" start-placeholder="Start date"
            end-placeholder="End date" />
    </div>
</template>

<script lang="ts" setup>
import { onBeforeMount, ref } from 'vue'
defineProps(['count'])
const emit = defineEmits(['update:count'])


const item = ref({
    date: []
})

onBeforeMount(() => {
    const res = { date1: '2020-08-18', date2: '2021-09-19' }
    item.value = {
        id: '1'
    }
    item.value.date = [res.date1, res.date2]
})

const handleClick = () => {
    emit('update:count', '2')
}
</script>