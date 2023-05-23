<template>
  <div>
      <h1>人员信息</h1>
      姓:<input type="text" v-model="person.firseName"><br>
      名:<input type="text" v-model="person.lastName"><br>
      全名:{{person.fullName}}<br>
      全名:<input type="text" v-model="person.fullName">
  </div>
</template>

<script>
  import { reactive , computed } from 'vue'
  export default {
    name: 'Demo',
    props:['name','school'],
    // computed:{
    //   fullName(){
    //     // vue2里看得到vue3数据，但vue2计算属性这种还是需要用到this调用
    //     return this.person.firseName + '-' + this.person.lastName
    //   }
    // },
    setup(){
        let person = reactive({
          firseName:'张',
          lastName:'三'
        })

        // 计算属性-简写写法(没有考虑计算属性被修改的情况)
        // person.fullName = computed(()=>{
        //   return person.firseName + '-' + person.lastName
        // })

        // 计算属性-完整写法(考虑了读和写的情况)
        person.fullName = computed({
          get(){
            return person.firseName + '-' + person.lastName
          },
          set(value){
            const nameArr = value.split('-')
            person.firseName = nameArr[0]
            person.lastName = nameArr[1]
            // person.fullName = person.firseName + '-' + person.lastName
          }
        })
        return {
          person,
          // fullName
        }
    }
  }
</script>

<style>

</style>
