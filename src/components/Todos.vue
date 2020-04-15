<template>
  <div>
    <hr>
    <div v-for="todo in todos" :key="todo.id">
      <TodoItem :todo="todo" v-on:deleteTodo="$emit('deleteTodo', todo.id)"/>
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem'

export default {
  name: 'Todos',
  props: ['todos'],
  components: {
    TodoItem
  }
}
</script>