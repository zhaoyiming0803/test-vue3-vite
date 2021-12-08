<script setup>
import { ref, onMounted, watch, computed, watchEffect } from 'vue'

defineProps({
  msg: String
})

const count = ref(0)

// 如果写的是 count * 100，则 sum 返回 NaN，下面对 sum watch 也是不生效的
const sum = computed(() => count.value * 100)

onMounted(() => {
  console.log('count: ', count)
})

// https://v3.cn.vuejs.org/guide/composition-api-introduction.html#watch-%E5%93%8D%E5%BA%94%E5%BC%8F%E6%9B%B4%E6%94%B9
watch(count, (newValue, oldValue) => {
  console.log('count new value: ', newValue)
  console.log('count old value: ', oldValue)
}, {
  deep: true,
  immediate: true
})

watch(sum, (newValue, oldValue) => {
  console.log('sum new value: ', newValue)
  console.log('sum old value: ', oldValue)
}, {
  deep: true,
  immediate: true
})
</script>

<template>
  <h1>{{ msg }}</h1>

  <p>
    Recommended IDE setup:
    <a href="https://code.visualstudio.com/" target="_blank">VSCode</a>
    +
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
  </p>

  <p>
    <a href="https://vitejs.dev/guide/features.html" target="_blank">
      Vite Documentation
    </a>
    |
    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Documentation</a>
  </p>

  <button type="button" @click="count++">count is: {{ count }}</button>
  <p>
    Edit
    <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
