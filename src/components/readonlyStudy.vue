<template>
    <div>
        <div>{{num}}</div>
        <button @click="num++">增加</button>
    </div>
</template>

<script>
import {ref, reactive, readonly, shallowReadonly} from "vue";

export default {
    name: "readonlyStudy",
    setup() {
        let num = ref(0)
        let n = readonly(num)


        let z = reactive({
            x: 0,
            y: 1,
            xy: {
                x: 0
            }
        })
        z = shallowReadonly(z)
        return {
            num,
            n,
            z
        }
    }
}
</script>

<style scoped>

</style>