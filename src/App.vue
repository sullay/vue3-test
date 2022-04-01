<script setup>
import HelloWorld from './components/HelloWorld.vue'
import { ref } from 'vue'
defineProps({
  count: Number
})
const hasTitle = ref(true)
</script>

<template>
  <div class="app">
    <HelloWorld :hasTitle="hasTitle" />
    <button type="button" @click="hasTitle=!hasTitle">确认</button>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
