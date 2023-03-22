<script>
export default {
  data() {
    return {
      title: "",
      todos: []
    }
  },
  methods: {
    add(data) {
      this.todos.push(data)
    }
  }
}
</script>

<script setup>
import TodoItem from './TodoItem.vue'
</script>

<template>
  <div class="card">
    <h1>Todo App</h1>
    <form>
      <div>
        <input type="text" v-model="title" />
        <button type="button" @click="add(title)">Add</button>
      </div>
    </form>
    <div>
      <ul v-for="todo in todos">
        <TodoItem :title="todo" />
      </ul>
    </div>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

.card {
  background-color: white;
  box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
  padding: 2rem 4rem;
}
</style>
