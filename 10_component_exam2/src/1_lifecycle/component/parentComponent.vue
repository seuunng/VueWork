<template>
    <div class="parent">
    Parent 컴퍼넌트  
        <div>
            <p>data.count = {{ count }}</p>
            <p>props.prop = {{ prop }}</p>
        </div>
        <div>
            <button @click="count++">data  변경</button>
            <button @click="prop++">prop  변경</button>
        </div>
  </div>
  <child-component :prop="prop"></child-component>
</template>

<script>
import childComponent from './childComponent.vue'

export default {
  components: { childComponent },
  data(){
    return{
    count : 1,
    prop : 1,
    }
  },

}
</script>

<style>
    .parent {
        border :1px solid #247247;
        margin: 10px;
    }
</style>