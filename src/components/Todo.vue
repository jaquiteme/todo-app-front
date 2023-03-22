<script>
export default {
  data() {
    return {
      title: "",
      todos: []
    }
  },
  methods: {
    add(event, data) {
      event.preventDefault()
      this.todos.push(data)
    }
  }
}
</script>

<script setup>
import TodoItem from './TodoItem.vue'
</script>

<template>
  <h2>My Todo</h2>
  <div class="card">
    <form style="display: flex; flex-flow: row wrap; align-items: center;">
      <div>
        <input class="form-control mb-2" type="text" v-model="title" />
      </div>
      <button style="margin-left: 1rem;" class="btn btn-primary mb-2" type="submit" @click="add($event, title)">
        Add
      </button>
    </form>
    <div>
      <TodoItem v-for="todo in todos" :title="todo" />
    </div>
  </div>
</template>

<style scoped>
h2 {
  font-weight: 500;
  font-size: 2rem;
  top: -10px;
}
</style>
