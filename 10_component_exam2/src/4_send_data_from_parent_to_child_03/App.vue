<template>
  <div id="app">
    <div>
      <h1></h1>
    </div>
    <div>
    </div>  
  </div>
  <!-- 부모에서 추가하 내용은 자식에게 상속된다. -->
  <!-- 컴포넌트 안에 태그가 여러개 있으면 상속이 안된다: 어디에 적용해야할지 판단할 수 없어서-->
  <my-button>MyButton</my-button>
  <my-button></my-button> <!--슬롯태그안에 디폴트값을 설정할수있다.-->
  <my-button class="mycss">MyButton</my-button>
  <my-button style="color: black">MyButton</my-button>
  <my-button>
    <span>(A)</span>
    <span>MyButton</span>
  </my-button>
  <my-button>
    <template v-slot:text>
        <span>MyButton</span>
    </template>
    <template #icon>
        <span>(A)</span>
    </template>
  </my-button>
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
    list:["memo1", "memo2"],
    count:2,
    }
  },
  methods:{
    addMemo(){
      this.count++;
      this.list.push("memo"+this.count);
    },
    selectedMemo(){
      
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