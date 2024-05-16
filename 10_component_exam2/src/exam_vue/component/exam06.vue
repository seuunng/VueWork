<template>
  <div id="app">
    <h1>간단한 계산기</h1>
    <input type="text" v-model.number="firstNum"><input type="text" v-model.number="secondNum"><br><br>
    <button @click="plus">덧샘계산</button>
    <button @click="minus">뺄샘계산</button>
    <button @click="multiply">곱샘계산</button>
    <button @click="divide">나눗샘계산</button><br><br>
    결과는 {{ this.result }}입니다.
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
      firstNum:0,
      secondNum:0,
      result:0,
    }
  },
  methods:{
    plus(){
      this.result=this.firstNum+this.secondNum;
    },
    minus(){
      this.result=this.firstNum-this.secondNum;
    },
    multiply(){
      this.result=this.firstNum*this.secondNum;
    },
    divide(){
      if(this.secondNum!=0){
      this.result=this.firstNum/this.secondNum;
      }else if(this.secondNum==0){
        alert("0으로 나눌수 없습니다.");
      }
    },
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