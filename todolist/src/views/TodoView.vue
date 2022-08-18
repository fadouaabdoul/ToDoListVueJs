<template>
  <div class="todolist">
    <todo></todo>
  </div>
</template>
<script>

  import todo from '@/components/todolist'

  export default {
    name: 'HomeView',
    components: {
      todo
    }
  }
</script>
