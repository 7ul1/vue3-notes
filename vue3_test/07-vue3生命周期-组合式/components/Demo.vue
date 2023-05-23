<template>
  <div>
     <h2>当前求和：{{sum}}</h2>
     <button @click="sum++">点我sum++</button>
  </div>
</template>

<script>
  import {
    ref,
    onBeforeMount,
    onMounted,
    onBeforeUpdate,
    onUpdated,
    onBeforeUnmount,
    onUnmounted
  } from 'vue'
  export default {
    name: 'Demo',
    setup(){
        let sum = ref(0)

        onBeforeMount(()=>{
          console.log('--onBeforeMount--');
        })
        onMounted(()=>{
          console.log('--onMounted--');
        })
        onBeforeUpdate(()=>{
          console.log('--onBeforeUpdate--');
        })
        onUpdated(()=>{
          console.log('--onUpdated--');
        })
        onBeforeUnmount(()=>{
          console.log('--onBeforeUnmount--');
        })
        onUnmounted(()=>{
          console.log('--onUnmounted--');
        })

        return {
          sum,
        }
    }
  }
</script>

<style>

</style>
