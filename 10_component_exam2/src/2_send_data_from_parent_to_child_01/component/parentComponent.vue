<template>
    <div class="parent">
    Parent 컴퍼넌트  
        <div>
            <button @click="addMemo">부모에서 자식으로 데이터 보내기</button>
        </div>
  </div>
  <child-component :list="list" ></child-component>
</template>

<script>
import childComponent from './childComponent.vue'

export default {
  name: 'parentComponent', //this.$options.name으로 출력할 수 있음
  components: { childComponent },
  data(){
    return{
      list:["memo1", "memo2", "memo3"],
      count:3,
    }
  },
  methods:{
    addMemo(){
      this.count++;
      this.list.push("memo"+this.count);
    },
  }

}
</script>

<style>
    .parent {
        border :1px solid #247247;
        margin: 10px;
    }
</style>