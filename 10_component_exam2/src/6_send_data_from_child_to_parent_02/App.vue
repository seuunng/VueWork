<template>
  <div id="app">
    <my-button @logChild="log">MyButton</my-button>
    <!-- 실제로는 div이고 mybutton자식컴포넌트기 때문에 
      클릭이벤트리스너를 달아도 실행이 안되야 하는거 아닌가?
      라는 의문이 들어야 하지만,
      자식에게 속성들이 그대로 상속된다는 규칙때문에 가능하다!
      
      자식컴포넌트에 버튼 말고 다른 태그를 만들면 상속이 어디로 해야할지 
      판단하지 못해서 상속이 안되는 특성으로 인해
      다른태그가 추가되면 클리 이벤트리스너도 동작하지 않는것을 확인 할 수 있다.-->
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
    }
  },
  methods:{
    log(message){
      alert("함수실행!");
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