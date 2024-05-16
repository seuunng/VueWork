<template>
  <div class="child">
    Child 컴퍼넌트  
        <ul >
          <li v-for="memo in list" @click="sendMemo(memo)">{{ memo }}</li>
        </ul>
  </div>
</template>

<script>
const ChildComponent ={ //변수선언
  data(){
    return{
      list:["memo1", "memo2", "memo3"],
      //memoselected:"",
    }
  },
  methods:{
    sendMemo(memo){
      this.$emit(ChildComponent.SELECT, memo);
    }
  }
}
ChildComponent.SELECT="select" //상수추가
export default ChildComponent; //상수를 포함한 변수들을 외부에서 사용할 수 있도록 전달
</script>

<style>
    .child {
        border :1px solid #000000;
        margin: 10px;
    }
</style>