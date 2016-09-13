<template>
  <div id="app">
    <Dragger></Dragger>
  </div>
</template>

<script>
import Dragger from './components/Dragger.vue'
export default {
  components: { Dragger },
}
</script>

<style>
html, body {
  overflow: hidden;
  background-color: #00bcd4;
  font-family: Helvetica, sans-serif;
}
</style>
