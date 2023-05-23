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

      <h1>{{job.a.b.c}}</h1>
      <hr>
      <h1>爱好:{{hoby}}</h1>
  </div>

</template>

<script>
  import { ref,reactive } from 'vue'
  export default {
    name: 'App',
    setup(){
      // 测试setup
      let name = ref('张三');
      let age = ref(18);
      let job = reactive({
        type:'小白程序员',
        wages:'1k',
        a:{
          b:{
            c:23123123
          }
        }
      })

      let hoby = reactive(['抽烟','喝酒','烫头'])

      function changeInfo(){
        // name.value = '小米'
        // age.value = 100
        // // console.log(job);
        // job.type = '后端程序员'
        // job.wages = '8000k'
        // job.a.b.c = 100
        hoby[0] = '学习'
      }

      return {
        name,
        age,
        changeInfo,
        job,
        hoby
      }
    }
  }
</script>

<style>

</style>
