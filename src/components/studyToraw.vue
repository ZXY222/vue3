<template>
<div>
  <div>{{aaa}}</div>
  <button @click="change">修改</button>
</div>
</template>

<script>
import {reactive, toRaw, ref, markRaw} from "vue";

export default {
  name: "studyToraw",
  setup() {
    let person = reactive({
      name: 'zxy',
      age: 23,
      job: {
        type: 'web'
      }
    })
    let aaa = ref({
      age: 23
    })
    function change() {
      let a = toRaw(aaa.value);
      console.log(a);
    }
    let info = {
      height: 175
    }
    person.info = markRaw(info)
    return {
      person,
      change,
      aaa
    }
  }
}
</script>

<style scoped>

</style>
