<script>
export default {
  data() {
    return {
      title: "",
      todos: [],
      editId: -1
    }
  },
  methods: {
    add: function (data) {
      if (data) {
        this.todos.push(data)
        this.title = ""
      }
    },
    remove: function (id) {
      this.todos.splice(id, 1)
    },
    edit: function (id, title = null) {
      if (!title) {
        this.title = this.todos[id]
        this.editId = id
      } else {
        this.todos.splice(id, 1, title)
        this.title = ""
        this.editId = -1
        console.log("Edited")
      }
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
      <button v-if="editId == -1" style="margin-left: 1rem;" class="btn btn-primary mb-2" type="submit"
        @click.enter.submit.prevent="add(title)">
        Add
      </button>
      <button v-if="editId > -1" style="margin-left: 1rem;" class="btn btn-warning mb-2" type="submit"
        @click.enter.submit.prevent="edit(editId, title)">
        Edit
      </button>
    </form>
    <div>
      <TodoItem v-for="value, index  in todos" :title="value" :index="index" :key="index" @remove="remove" @edit="edit" />
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
