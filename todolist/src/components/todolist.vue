<template>
  <div class="todolist">
    <h1>To Do List with VueJs</h1>
    <input @keyup.enter="add" v-model="title" type="text" placeholder="what do you wanna do today?">
    <button @click="add">Add</button>

    <ul>
      <li v-for="todo in todos" :key="todo">{{todo}}</li>
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
        'do something'
      ]
    }
  },
  methods:{
    add(){
      this.todos.push(this.title);
      this.title = ""


      console.log(JSON.stringify(this.todos))
    }
  }


}
</script>

<style scoped>

</style>
