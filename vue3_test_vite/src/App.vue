<template>
    <h1>我是APP组件</h1>
</template>

<script>

export default {
  name: 'App',
  setup(){
    // 测试setup
    let name = '张三';
    let age = 18

    function sayHello(){
        alert(`我叫${name}，今年${age}岁`)
    }
  }
}
</script>

<style>

</style>
