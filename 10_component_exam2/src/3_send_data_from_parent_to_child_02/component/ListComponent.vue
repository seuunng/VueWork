<template>
    <div class="parent">
        <div v-for="memo in list" @click="selectedMemo(memo)">
          <div>{{ memo }}</div>
        </div>
  </div>
  
</template>

<script>

export default {
  name: 'ListComponent', 
   props:{
        list:{
          type: Array,
        }    
    },
  methods: {
    selectedMemo(memo) {
      this.$emit('selectedMemo', memo);
    }
  }
}
</script>

<style>
    .parent {
        border :1px solid #247247;
        margin: 10px;
    }
</style>