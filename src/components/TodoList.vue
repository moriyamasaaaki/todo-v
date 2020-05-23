<template>
  <div clas="todo-list">
      <TodoItem />
      <TodoItem />
      <TodoItem />
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem'
export default {
  components: {
    TodoItem
  }
}
</script>

<style lang="scss" scoped>
.message {
  margin: 40px 0;
}
</style>
