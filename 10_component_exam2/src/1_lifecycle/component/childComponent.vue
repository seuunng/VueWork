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
    name: 'childComponent', //this.$options.name으로 출력할 수 있음
    data(){
        return{
        count: 1,
        }
    },
    props:{
        prop:{
            type:Number,
        }
    },
  beforeCreate(){
    console.log("2.beforeCreate : ", this.$options.name)
  },
  created(){
    console.log("2.created : ", this.$options.name)
  },
  beforeMount(){
    console.log("2.beforeMount : ", this.$options.name)
  },
  mounted(){
    console.log("2.mounted : ", this.$options.name)
  },
  beforeUpdate(){
    console.log("2.beforeUpdate : ", this.$options.name)
  },
  updated(){
    console.log("2.updated : ", this.$options.name)
  },
  beforeUnmount(){
    console.log("2.beforeUnmount : ", this.$options.name)
  },
  unmounted(){
    console.log("2.unmounted : ", this.$options.name)
  },
  beforeDestroy(){
    console.log("2.beforeDestroy : ", this.$options.name)
  },
  destroyed(){
    console.log("2.destroyed : ", this.$options.name)
  },
}
</script>

<style>
    .child {
        border :1px solid #000000;
        margin: 10px;
    }
</style>