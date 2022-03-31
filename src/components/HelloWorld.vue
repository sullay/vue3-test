<script setup>
import test1 from './test1.vue'
import { ref, nextTick } from 'vue'

defineProps({
  msg: String
})

const count = ref(0)
const hasTitle = ref(true)
const test = () => {
  if (count.value >= 50000) {
    console.log('完成');
    return;
  }
  count.value++
  nextTick(() => {
    test()
  })
}
</script>

<template>
  <test1 :count="count" :hasTitle="hasTitle"/>
  <button type="button" @click="test">+1</button>
  <br/>
  <button type="button" @click="hasTitle=!hasTitle">确认</button>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
