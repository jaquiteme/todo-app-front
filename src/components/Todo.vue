<template>
  <div id="todo-card">
    <h1>Todo App</h1>
    <form>
      <div>
        <input type="text" v-model="title"/>
        <button type="button" @click="add(title)">Add</button>
      </div>
    </form>
    <div>
      <ul v-for="todo in todos">
        <li>{{ todo }}</li>
      </ul>
    </div>
  </div>
</template>

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

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

</style>
