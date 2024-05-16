<template>
  <div class="parent">
    Parent 컴퍼넌트  
    <child-component  ref="child" :cnt_fst="cnt_fst"></child-component>
  </div>
</template>

<script>
import childComponent from './childComponent.vue'

export default {
  name: 'parentComponent', //this.$options.name으로 출력할 수 있음
  components: { childComponent },
  data(){
    return{
      
    }
  },
  methods:{
  }

}
</script>

<style>
    .parent {
        border :1px solid #247247;
        margin: 10px;
        background-color:cadetblue;
    }
</style>