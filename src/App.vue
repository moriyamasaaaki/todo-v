<template>
  <div id="app">
    <div class="todo-wrapper">
      <div class="todo-container">
        <TodoList />
      </div>
    </div>
  </div>
</template>

<script>
import 'bulma/css/bulma.css';
import TodoList from '@/components/TodoList'
export default {
  components: {
    TodoList
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