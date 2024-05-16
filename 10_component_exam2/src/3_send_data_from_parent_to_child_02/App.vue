<template>
  <div id="app">
    <div>
      <h1>메모 추가</h1>
    </div>
    <div>
      <p><button @click="addMemo">메모 추가</button></p>
    </div>  
    <list-component :list="list" @selectedMemo="updatedSelectedMemo"></list-component>
    <view-component :selectedMemo="selectedMemo"></view-component>
  </div>
</template>

<script>
import ListComponent from './component/ListComponent.vue'
import ViewComponent from './component/ViewComponent.vue'
export default {
  components: { 
    ListComponent,
    ViewComponent
   },
  name:'App',
  data(){
    return{
    list:["memo1", "memo2"],
    count:2,
    selectedMemo:"",
    }
  },
  methods:{
    addMemo(){
      this.count++;
      this.list.push("memo"+this.count);
    },
    updatedSelectedMemo(memo){
      this.selectedMemo = memo;
    }
  }
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