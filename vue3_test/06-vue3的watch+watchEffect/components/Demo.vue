<template>
  <div>
     <h2>当前求和：{{sum}}</h2>
     <button @click="sum++">点我sum++</button>
     <hr>
     <h2>当前信息为：{{msg}}</h2>
     <button @click="msg+='!'">修改信息</button>
     <hr>
     <h2>姓名：{{person.name}}</h2>
     <h2>年龄：{{person.age}}</h2>
     <h2>薪资：{{person.job.j1.salary}}</h2>
     <button @click="person.name+='@'">修改姓名</button>
     <button @click="person.age++">修改年龄</button>
     <button @click="person.job.j1.salary++">修改薪资</button>
  </div>
</template>

<script>
  import { ref , reactive , watch , watchEffect } from 'vue'
  export default {
    name: 'Demo',
    props:['name','school'],
    setup(){
        let sum = ref(0)
        let msg = ref('小明啊')
        let person = reactive({
          name:'张三',
          age:18,
          job:{
            j1:{
              salary:20
            }
          }
        })

        // 情况一：监视ref所定义的一个响应式数据
        // watch(sum,(newValue,lastValue)=>{
        //   console.log(newValue,lastValue);
        // },{
        //   immediate:true,
        //   // deep:true
        // })

        // 情况二：监视ref所定义的多个响应式数据
        // watch([sum,msg],(newValue,lastValue)=>{
        //   // console.log(newValue,lastValue);
        //   console.log('sum或msg变了');
        // })

        /* 
          情况三：监视reactive所定义的一个响应式数据,
          注意：1.无法正常获得oldValue  
          注意：2.强制开启了深度检测 deep配置无效
        
        */
        // watch(person,(newValue)=>{
        //   console.log(newValue);
        // })

        // 情况四：监视reactive所定义的一个响应式数据中的某一个属性,
        // watch(()=>person.age,(newValue)=>{
        //   console.log(newValue);
        // })

        // 情况五：监视reactive所定义的多个响应式数据,
        // watch([()=>person.name,()=>person.age],(newValue)=>{
        //   console.log(newValue);
        // })

        // watch(()=>person.job,(newValue)=>{
        //   console.log(newValue);
        // },{
        //   deep:true // 此处由于监视的是reactive所定义的对象中的某个属性，所以deep有效(监听的对象里的这个属性还是个对象)
        // })

        watchEffect(()=>{
          const x1 = sum.value
          console.log('watchEffect调用了');
        })

        return {
          sum,
          msg,
          person
        }
    }
  }
</script>

<style>

</style>
