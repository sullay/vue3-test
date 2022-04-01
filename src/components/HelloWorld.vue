<script setup>
import test1 from './test1.vue'
import { ref, nextTick } from 'vue'

defineProps({
  msg: String
})

const count = ref(1)
const hasTitle = ref(true)
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
  <div className="app">
    <test1 :count="count" :hasTitle="hasTitle"/>
    <button type="button" @click="addNum">+1</button>
    <br/>
    <button type="button" @click="hasTitle=!hasTitle">确认</button>
  </div>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
