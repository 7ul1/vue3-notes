<template>
  <Demo name="小明" school="尚硅谷" />
</template>

<script>
  // 引入别的插件或方法可以套一个大括号{} 对引入的组件不需要加 
  import Demo from './components/Demo.vue'
  export default {
    name: 'App',
    components:{ Demo },

  }
</script>

<style>

</style>
