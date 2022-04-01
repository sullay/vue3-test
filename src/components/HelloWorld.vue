<script setup>
import test from './test.vue'
import { ref, nextTick } from 'vue'

defineProps({
  hasTitle: Boolean
})

const count = ref(1)
let start;
const addNum = () => {
   if(count.value ===1)  start = performance.now();
  if (count.value >= 50000) {
    console.log(performance.now() - start);
    console.log('完成');
    return;
  }
  count.value++
  nextTick(() => {
    addNum()
  })
}
</script>

<template>
  <div>
    <h1 v-if="hasTitle">test</h1>
    <h2 v-else>没有title</h2>
    <test :count="count"/>
    <button type="button" @click="addNum">+1</button>
  </div>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
