<template>
  <div class="sample" @click="addCount">
    {{ count }} 
  </div>
</template>

<script>

export default {
  name: 'sampleComponent', 
  components: {  },
  data(){
    return{
      count: 1,
    }
  },
  methods:{
    addCount(){
      this.count++;
    }
  }

}
</script>

<style>
    .sample {
        border :1px solid gray;
        margin: 10px;
        background-color: peru;
    }
</style>