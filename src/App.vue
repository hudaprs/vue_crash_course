<template>
  <div id="app">
    <Header />
    <AddTodo :todos="todos" v-on:addTodo="createTodo"/>
    <Todos :todos="todos" v-on:deleteTodo="removeTodo" />
  </div>
</template>

<script>
import Header from './components/Layout/Header'
import AddTodo from './components/AddTodo'
import Todos from './components/Todos'

export default {
  name: 'App',
  components: {
    Header,
    AddTodo,
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'Learn VueJS',
          completed: false,
        },
        {
          id: 2,
          title: 'Learn VueX',
          completed: false
        },
        {
          id: 3,
          title: 'Learn Xpress',
          completed: false
        }
      ]
    }
  },
  methods: {
    createTodo(newTodo) {
      this.todos = [...this.todos, newTodo]
    },
    removeTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
  }
}
</script>

<style>
  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
</style>