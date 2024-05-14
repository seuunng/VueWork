<template>
  <div class="child">
    Child 컴퍼넌트  
        <div>
            <p>data.count = {{ count }}</p>
            <p>props.prop = {{ prop }}</p>
        </div>
        <div>
            <button @click="count++">data  변경</button>
        </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
        count: 1,
        }
    },
    props:{
        prop:{
            type:Number,
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