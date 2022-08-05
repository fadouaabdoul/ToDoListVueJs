<template>
  <div class="todolist">
    <h1>To Do List with VueJs</h1>
    <input @keyup.enter="add" v-model="title" type="text" placeholder="what do you wanna do today?">
    <button @click="add">Add</button>

    <ul>
      <li v-for="(todo, index) in todos" :key="todo">{{todo}}
        <span @click="remove(index)" class="remove">X</span>
      </li>

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
    },

    remove(index){

      console.log(index)
      this.todos.splice(index,1)
    }

  }


}
</script>

<style scoped>
 .remove{
   padding: .3rem .6rem;
   cursor: pointer;
   background-color: darkred;
   border-radius: 40px;
 }

</style>
