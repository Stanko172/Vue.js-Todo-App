<template>
  <div id="app">
    <Header />
    <Todos />
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
