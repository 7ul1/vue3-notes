<template>
  <div>
      <button @click="isShowDemo= !isShowDemo">显/隐</button>
      <Demo v-if="isShowDemo" />
  </div>
</template>

<script>
import { ref } from 'vue'
  // 引入别的插件或方法可以套一个大括号{} 对引入的组件不需要加 
  import Demo from './components/Demo.vue'
  export default {
    name: 'App',
    components:{ Demo },
    setup(){
      const isShowDemo = ref(true)
      return{
        isShowDemo
      }
    }
  }
</script>

<style>

</style>
