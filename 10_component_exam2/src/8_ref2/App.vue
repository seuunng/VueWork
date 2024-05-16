<template>
  <div id="app">
    <div>
      <h1>참조하기</h1>
    </div>
    <div>
      <!-- 클릭하면 sam1의 카운트값 콘솔출력 -->
      <button @click="getCount1">1번째 카운트값 알아내기</button><br>
      <!-- 클릭하면 sam2의 카운트값 콘솔출력 -->
      <button @click="getCount2">2번째 카운트값 알아내기</button><br>
      <!-- 클릭하면 입력 필드창으로 커서 이동 -->
      <button @click="getInput1">input1 포커스 이동</button><br>
    </div>  
    <div>
      <sample-component ref="sam1" ></sample-component>
      <sample-component ref="sam2"></sample-component>
    </div>
    <parent-component ref="parent"></parent-component>
  </div>
</template>

<script>
import parentComponent from './component/parentComponent.vue'
import SampleComponent from './component/sampleComponent.vue'
export default {
  components: { parentComponent, SampleComponent },
  name:'App',
  data(){
    return{
      cnt_fst: 0,
      cnt_scd: 0,
    }
  },
  methods:{
    getCount1(){
      //이렇게 콘솔로 찍어서 $refs뒤에 어떤 옵션을 둘수 있는지 확인 가능
      console.log(this.$refs)
      //cnt_fst에 sam1의 count값을 저장한다.
      this.cnt_fst=this.$refs.sam1.count;
      //그리고 cnt_fst를 콘솔 출력
      console.log("1번째 카운트 값 :"+this.cnt_fst)
    },
    getCount2(){
      this.cnt_scd=this.$refs.sam2.count;
      console.log("2번째 카운트 값 :"+this.cnt_scd)
    },
    getInput1(){
      //앱에서 부터 입력 필드 창까지
      //앱에서 부모컴포넌트 참조-> 부모에서 자식컴포넌트 참조->
      //자식에서 입력필드 태그 참조->포커스 함수 실행
      this.$refs.parent.$refs.child.$refs.input1.focus();
      //같은 경로의 값을 ""로 저장, 결과적으로 입력필드창 초기화
      this.$refs.parent.$refs.child.$refs.input1.value="";
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