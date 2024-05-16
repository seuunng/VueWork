<template>
  <div id="app">
    <div>
      <h1>자식에서 부모로 데이터 보내기</h1>
    </div>
    <div>
    </div>  
    <parent-component></parent-component>
  </div>
</template>

<script>
import parentComponent from './component/parentComponent.vue'
export default {
  components: { parentComponent },
  name:'App',
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