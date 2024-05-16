<template>
  <div class="child">
        <div >
          선택된 메모 : {{ selectedMemo }}
        </div>
  </div>
</template>

<script>
export default {
    name: 'viewComponent', 
    data(){
        return{
        }
    },
    props:{
      selectedMemo:{
          type: String,
        },

    }
}
</script>

<style>
    .child {
        border :1px solid #000000;
        margin: 10px;
    }
</style>