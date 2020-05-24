<template>
  <div clas="todo-list">
      <TodoItem
        v-for="todo in todos"
        :key="todo._id"
        :_id="todo._id"
        :title="todo.title"
        :description="todo['description']"
       />
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem'
export default {
  components: {
    TodoItem
  },
  props: {
    todos: {
        required: true,
        type: Array
    }
  }
}
</script>

<style lang="scss" scoped>
.message {
  margin: 40px 0;
}
</style>
