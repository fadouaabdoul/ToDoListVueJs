<template>
  <div class="todolist">
    <h1>To Do List with VueJs</h1>
    <input type="text"  placeholder="what do you wanna do today?">
    <button @click="add">Add</button>

    <ul>
      <li v-for="todo in todos" :key="todo.task">{{todo.task}}</li>
    </ul>

  </div>
</template>

<script>
export default {
  name: 'todo-list',
  props: {},

  data(){
    return {
      title: [],
      todos: [
        { task: 'do something' }
      ]
    }
  },
  methods:{
    add(){
      this.todos.push( {});


      console.log(JSON.stringify(this.todos))
    }
  }


}
</script>

<style scoped>

</style>
