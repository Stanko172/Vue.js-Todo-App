<template>
  <div id="app">
    <Header />
    <Todos 
      :todos="todos"
      @delete-todo="deleteTodo"
      @new-todo="addTodo"
    />
  </div>
</template>

<script>
import Header from './components/layout/Header.vue'
import Todos from './components/todos/Todos.vue'

export default {
  name: 'App',
  components: {
    Header,
    Todos
    
  },
  data(){
    return {
      todos: [
      {
        id: 1,
        title: 'Todo one',
        completed: false
      },
      {
        id: 2,
        title: 'Todo two',
        completed: false
      },
      {
        id: 3,
        title: 'Todo three',
        completed: false
      }
    ]
    }
    
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id)
      console.log(this.todos)
    },
    addTodo(newTodo){
      this.todos.push(newTodo)
    }
  }
}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
  font-family: Arial, Helvetica, sans-serif;
}
</style>
