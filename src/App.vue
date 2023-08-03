<template>
  <div id="app">
    <HelloWorld :allOptions="dataList" :props="{ multiple: true }" filterable :loadSize="100"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import {dataList} from "./components/data1"
export default {
  name: 'App',
  data() {
    return {
      dataList
    }
  },
  components: {
    HelloWorld
  },
  mounted() {
    console.log('212121', dataList);
    for (var i = 1; i <= 2000; i++) {
          let obj = {value: 12+i, label: `测试${i}`}
          dataList[0].children.push(obj)
          // dataList[1].children.push(obj)
          // dataList[2].children.push(obj)
      }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
