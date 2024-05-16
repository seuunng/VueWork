<template>
  <div id="app">
    <h1>숫자 배열 조작과 구구단 출력</h1>
      <ul v-for="(num, index) in list" :key="index">
        <li>{{ num }} <button @click="update(index)">변경</button><button @click="del(index)">삭제</button></li>
      </ul>
      <button @click="add">추가</button><button @click="sort">소트</button><button @click="show">구구단보이기</button>
      <ul v-for="(num, index) in showTable" :key="index">
        <li>{{ num }}</li>
      </ul>
  </div>
</template>
  

<script>
import MyButton from './component/MyButton.vue';
export default {
  components: {
    MyButton 
   },
  name:'App',
  data(){
    return{
      list :[2,3,4,5,6,7,8,9],
      showTable :[],
    }
  },
  methods:{
    update(index){
      this.list[index]+=1;
      console.log(index);
    },
    del(index){
      this.list.splice(index, 1);
    },
    add(){
      this.list.push(this.list.length+2);
    },
    sort(){
      this.list.sort((a, b) => a - b);
    },
    show(){
      for(let i =0; i<this.list.length ; i++){
        for(let j=1; j<=9; j++){
          this.showTable.push(this.list[i]+'*'+j+'='+this.list[i]*j);
        } 
        
      }
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
.mycss {
  background-color: red;
}
</style>