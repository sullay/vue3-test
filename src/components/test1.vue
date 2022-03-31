<script setup>
defineProps({
  count: Number,
  hasTitle: false
})
</script>

<template>
  <h1 v-if="hasTitle">test</h1>
  <h2 v-else>没有title</h2>
  <div>计数: {{ count }}</div>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
