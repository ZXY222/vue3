<template>
    <div>
        <h3>{{ x }}</h3>
        <button @click="x++">增加</button>
    </div>
</template>

<script>
import { shallowReactive, shallowRef} from "vue";

export default {
    name: "shallowStudy",
    setup() {
        let x = shallowRef(0) // 响应式的
        // 非响应式
        let y = shallowRef({
            x: 0
        })

        // 只有第一层是响应式的，第二层不是
        let z = shallowReactive({
            x: 0,
            y: 1,
            xy: {
                x: 0
            }
        })
        return {
            z,
            y,
            x
        }
    }
}
</script>

<style scoped>

</style>