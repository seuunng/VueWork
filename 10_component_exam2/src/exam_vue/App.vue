<template>
<div id="app">
    <p> {{count}} </p>
    <input type="button" value="1씩 증가" @click="counting"/>
</div>
</template>
  

<script>
import MyButton from './component/MyButton.vue';
export default {
  name:'App',
  data(){
    return{
      count:1,
    }
  },
  methods:{
      counting(){
        this.count++;
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
.mycss {
  background-color: red;
}
</style>