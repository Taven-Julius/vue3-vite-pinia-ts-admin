<script setup lang="ts">
import { onMounted } from 'vue-demi'
import { RouterView } from 'vue-router'


onMounted(() => {
  let list =  [
        { id: 1, name: "101" },
        { id: 1, name: "102" },
        { id: 2, name: "201" },
        { id: 2, name: "202" },
        { id: 2, name: "203" },
        { id: 3, name: "301" },
      ];
  // 把list中id同样的数据放到一个数组中
  // let result = list.reduce((acc, cur) => {
  //   if (!acc[cur.id]) {
  //     acc[cur.id] = [];
  //   }
  //   acc[cur.id].push(cur);
  //   return acc;
  // }, []); 

  let map = new Map()
  list.forEach(item => {
    if (!map.has(item.id)) {
      map.set(item.id, [])
    }
    map.get(item.id).push(item)
    console.log(map);
    
  } )

  console.log(Array.from(map));



  

  
  
})

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
    background: orange;
    text-align: center;
  }

  .el-header {
    background: #c6e2ff;
  }
}
</style>
