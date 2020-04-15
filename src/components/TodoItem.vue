<template>
  <div class="todo-item" :class="{'is-completed': todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      {{ todo.title }}
      <button class="del" @click="$emit('deleteTodo', todo.id)">
        X
      </button>
    </p>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['todo'],
  methods: {
    markComplete() {
      return this.todo.completed = !this.todo.completed
    }
  }
}
</script>

<style>
  .todo-item {
    padding: 10px;
    background: #f4f4f4;
    border-bottom: 1px #ccc dotted;
  }

  .is-completed {
    text-decoration: line-through; 
  }

  .del {
    background: #ff0000;
    color: #fff;
    padding: 5px 9px;
    border: none;
    border-radius: 50%;
    float: right;
    cursor: pointer;
  }
</style>