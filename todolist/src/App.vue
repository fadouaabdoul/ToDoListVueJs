<template>
    <headermain/>
    <todolist/>
</template>

<script>
import todolist from './components/todolist.vue'
import headermain from './components/header.vue'

export default {
  name: 'App',
  components: {
    todolist,
      headermain
  }
}
</script>

<style>

</style>
