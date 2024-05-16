<template>
  <div class="child">
    Child 컴퍼넌트  
        <div >
          입력값 : <input type="text" v-model="value" ref="input1"/>
        </div>
  </div>
</template>

<script>
export default {
    name: 'childComponent', 
    data(){
        return{
        value: "sample",
        }
    },
  props:{
    cnt_fst:{
      type: Number,
    }
  },
}
</script>

<style>
    .child {
        border :1px solid #000000;
        margin: 10px;
        background-color: aliceblue;
    }
</style>