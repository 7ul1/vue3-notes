<template>

  <div>
      <h1>人员信息</h1>
      <h2>姓名:{{name}}</h2>
      <h2>年龄:{{age}}</h2>
      <hr>
      <h1>职业:{{job.type}}</h1>
      <h1>工资:{{job.wages}}</h1>
      <hr>
      <button @click="changeInfo">更改INFO</button>
  </div>

</template>

<script>
  import { ref } from 'vue'
  export default {
    name: 'App',
    setup(){
      // 测试setup
      let name = ref('张三');
      let age = ref(18);
      let job = ref({
        type:'小白程序员',
        wages:'1k',
        objc:{
          a:100,
          b:{
            c:1000
          }
        }
      })

      function changeInfo(){
        name.value = '小米'
        age.value = 100
        console.log(job.value);
        // job.value.type = '后端程序员'
        // job.value.wages = '8000k'
      }

      return {
        name,
        age,
        changeInfo,
        job
      }
    }
  }
</script>

<style>

</style>
