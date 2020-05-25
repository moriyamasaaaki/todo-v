<template>
  <div clas="todo-list">
    <div v-if="todos && todos.length > 0">
      <todo-item
        v-for="todo in todos"
        :key="todo._id"
        :_id="todo._id"
        :title="todo.title"
        :description="todo['description']"
      />
    </div>
    <div v-else class="no-todos">Todoがありません。作成してください。</div>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem";
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
};
</script>

<style lang="scss" scoped>
.message {
  margin: 40px 0;
}
.no-todos {
    padding: 20px;
    font-size: 24px;
    font-weight: bold;
    text-align: center;
}
</style>
