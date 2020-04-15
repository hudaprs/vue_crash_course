<template>
  <div>
    <form @submit.prevent="addTodo">
      <input type="text" v-model="title" placeholder="Add Todo...">
      <button type="submit" class="btn">
        Submit
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'AddTodo',
  props: ['todos'],
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTodo() {
      if(this.title == '') {
        return false
      } else {
        const newTodo = {
          id: this.todos.length + 1,
          title: this.title,
          completed: false
        }
        // Send To Parent
        this.$emit('addTodo', newTodo)
        this.title = ''
      }
    }
  }
}
</script>

<style>
  form {
    display: flex;
  }

  input[type=text] {
    padding: 5px;
    flex: 10;
  }

  button {
    flex: 2;
  }
  
  .btn {
    display: inline-block;
    background: #555;
    color: #fff;
    cursor: pointer;
    padding: 9px 20px;
    border: none;
  }

  .btn:hover {
    background: #666;
  }
</style>