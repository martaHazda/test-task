<template>
  <div id="app">
    <PostTruck />
  </div>
</template>

<script>
import PostTruck from './components/PostTruck.vue'

export default {
  name: 'app',
  components: {
    PostTruck
  }
}
</script>

<style>
#app {
  background-color: #c6dbec;
}
</style>
