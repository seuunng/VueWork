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
  name: 'parentComponent', //this.$options.name으로 출력할 수 있음
  components: { childComponent },
  data(){
    return{
    count : 1,
    prop : 5,
    }
  },
  beforeCreate(){
    console.log("1.beforeCreate : ", this.$options.name)
  },
  created(){
    console.log("1.created : ", this.$options.name)
  },
  beforeMount(){
    console.log("1.beforeMount : ", this.$options.name)
  },
  mounted(){
    console.log("1.mounted : ", this.$options.name)
  },
  beforeUpdate(){
    console.log("1.beforeUpdate : ", this.$options.name)
  },
  updated(){
    console.log("1.updated : ", this.$options.name)
  },
  beforeUnmount(){
    console.log("1.beforeUnmount : ", this.$options.name)
  },
  unmounted(){
    console.log("1.unmounted : ", this.$options.name)
  },
  beforeDestroy(){
    console.log("1.beforeDestroy : ", this.$options.name)
  },
  destroyed(){
    console.log("1.destroyed : ", this.$options.name)
  },

}
</script>

<style>
    .parent {
        border :1px solid #247247;
        margin: 10px;
    }
</style>