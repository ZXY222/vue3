<template>
<div>
  <input type="text" v-model="say">
  <h3>{{say}}</h3>
</div>
</template>

<script>
import {customRef} from "vue";

export default {
  name: "studyCustomRef",
  setup() {
    // 自定义一个响应式数据
    let say = myRef('hello')
    
    // 自定义方法
    function myRef(value) {
      // customRef接收一个函数作为参数，track进行数据追踪， trigger进行触发改动
      return customRef((track, trigger)=>{
        return {
          get() {
            // 进行数据追踪
            track()
            return value
          },
          set(newValue) {
            // 可以自定义对数据的一些操作
            value = newValue
            // 通知数据进行改变
            trigger()
          }
        }
      })
    }
    return {
      say
    }
  }
}
</script>

<style scoped>

</style>
