<template>
  <div id="app">
    <todo-create @formSubmitted="createTodo" />
    <div class="todo-wrapper">
      <div class="todo-container">
        <TodoList :todos="todos" />
      </div>
    </div>
  </div>
</template>

<script>
import "bulma/css/bulma.css";
import TodoList from "@/components/TodoList";
import TodoCreate from "@/components/TodoCreate";
import store from '@/store'
export default {
  components: {
    TodoList,
    TodoCreate
  },
  data() {
    return {
      todos: store.state.todos
};
  },
  methods: {
    createTodo(todo) {
      store.dispatch('createTodo', todo)    }
  }
};
</script>

<style lang="scss" scoped>
.todo-wrapper {
  max-width: 700px;
  margin: 0 auto;
  padding: 0 8px;
}
</style>