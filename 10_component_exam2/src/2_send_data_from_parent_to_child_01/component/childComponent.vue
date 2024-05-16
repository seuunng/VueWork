<template>
  <div class="child">
    Child 컴퍼넌트  
        <div>
          <ul v:for="list in list">
            <li>{{ list }}</li>
          </ul>
        </div>
  </div>
</template>

<script>
export default {
    name: 'childComponent', //this.$options.name으로 출력할 수 있음
    data(){
        return{
        count: 1,
        }
    },
    props:{
        list:{
          type: Array,
        }
        
    }
}
</script>

<style>
    .child {
        border :1px solid #000000;
        margin: 10px;
    }
</style>