<template>
<div>
  <h3>{{name}}</h3>
  <button @click="name+='!!!'">修改</button>
</div>
</template>

<script>
import {reactive, toRef, toRefs} from 'vue'
export default {
  name: "studyTorefs",
  setup() {
    let person = reactive({
      name: 'zxy',
      age: 23,
      job: {
        type: 'web'
      }
    })
    let p = toRefs(person)
    let name = toRef(person, 'name')
    return {
      ...toRefs(person)
    }
  }
}
</script>

<style scoped>

</style>
