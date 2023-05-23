<template>

  <div>
      <h1>人员信息</h1>
      <h2>姓名:{{name}}</h2>
      <h2>年龄:{{age}}</h2>
      <button @click="sayHello">说话</button>
      <br>
      <br>
      <button @click="getThree">点击获取vue3的数据</button>
      <br>
      <br>
      <button @click="thorwA">点击弹出a</button>

  </div>

</template>

<script>
import { h } from 'vue'
export default {
  name: 'App',
  data(){
    return{
      a:100,
      b:200
    }
  },
  methods:{
    getThree(){
      console.log(this.name);
      console.log(this.age);
    },
    thorwA(){
      console.log(this.a);
    }
  },
  setup(){
    // 测试setup
    let name = '张三';
    let age = 18;
    let a = 200

    function sayHello(){
        alert(`我叫${name}，今年${age}岁`)
    }



    return {
      name,
      age,
      sayHello,
      a
    }

    // return ()=> h('h1','小米')
  }
}
</script>

<style>

</style>
