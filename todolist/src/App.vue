<template>
    <headermain/>
    <slider/>
    <todolist/>
</template>

<script>
import todolist from './components/todolist.vue'
import headermain from './components/header.vue'
import slider from './components/slider'

export default {
  name: 'App',
  components: {
    todolist,
      headermain,
      slider
  }
}
</script>

<style>

</style>
