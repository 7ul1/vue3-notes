<template>
  <div>
     <h2>当前求和：{{sum}}</h2>
     <button @click="sum++">点我sum++</button>
  </div>
</template>

<script>
  import {
    ref,
    reactive,
    onMounted,
    readonly,
  } from 'vue'

  export default {
    name: 'Demo',
    setup(){
      let sum = ref(0)
      // const sum = ref(0)
      sum = readonly(sum)
      return {
        sum,
      }
    }
  }
</script>

<style>

</style>
