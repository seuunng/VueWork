<template>
    <div class="btn">
        <slot></slot>
    </div>
    <h1 @click="onclick">Test</h1>
    <input type="text" v-model="text"/>
</template>

<script>
export default {
    emits : ["logChild"],
    methods:{
      onclick(){
        this.$emit('logChild','message')
      },
      
    }
}
</script>

<style>
    .btn {
        display: inline-block;
        padding: 6px;
        margin: 4px;
        border-radius: 4px;
        background-color: gray;
        color: white;
        cursor:pointer;
    }
</style>