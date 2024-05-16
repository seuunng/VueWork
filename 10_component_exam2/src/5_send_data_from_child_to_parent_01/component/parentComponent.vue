<template>
    <div class="parent">
    Parent 컴퍼넌트  
        <div>
          자식에게서 받은 데이터  {{ selectedMemo }}
        </div>
  <child-component @select="onSelectedMemo"></child-component>
  <!--여기서 @select는 childComponent가 에서 생성한 상수에 연결됨 
    상수를 click으로 해서 사용할 수 도 있지만 그러면 childComponent의 모든 부분을 클릭해도 해당 함수가 실행될 수 있다.
    childComponent에서 클릭하면 sendMemo() 함수가 실행됨
    this.$emit(ChildComponent.SELECT, memo);
    여기서 ChildComponent.SELECT가 부모컴퍼넌트에 @select를 발동시켜서
    onSelectedMemo메서드가 실해된다.-->
  <!--  : 바인딩 속성을 설정, v-bind 디렉티브의 줄임말
        @ 이벤트 리스너를 등록
        # v-slot 디렉티브의 줄임말로 사용-->
  </div>
</template>

<script>
import childComponent from './childComponent.vue'

export default {
  name: 'parentComponent',
  components: { childComponent },
  data(){
    return{
      selectedMemo:"",
    }
  },
  methods:{
    onSelectedMemo(memo){
      this.selectedMemo=memo;
    }
  }
}
</script>

<style>
    .parent {
        border :1px solid #247247;
        margin: 10px;
    }
</style>