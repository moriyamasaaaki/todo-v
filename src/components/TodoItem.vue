<template>
  <div class="todo-item">
    <article v-if="!editMode" class="message">
      <div class="message-header">
        <p>{{ title }}</p>
        <button class="delete" aria-label="delete"></button>
      </div>
      <div class="message-body">{{ description }}</div>
      <div class="buttons">
        <button @click="editMode = true" class="button is-warning">編集</button>
        <button @click="deleteTodo = true" class="button is-warning">削除</button>
      </div>
    </article>
    <form v-else action>
      <div class="field">
        <label class="label">タイトル</label>
        <div class="control">
          <input :value="title" class="input" type="text" placeholder="Text input" />
        </div>
      </div>
      <div>
        <label class="label">内容</label>
        <div class="control">
          <textarea
            :value="description"
            class="textarea"
            placeholder="10 lines of textarea"
            rows="10"
          ></textarea>
        </div>
      </div>
      <div class="buttons">
        <button @click.prevent="editTodo" class="button is-warning">更新</button>
        <button @click.prevent="editMode = false" class="button is-warning">キャンセル</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      editMode: false
    };
  },
  methods: {
    editTodo() {
      alert("editing todo!");
    },
    deleteTodo() {
      alert("deleting todo!");
    }
  }
};
</script>

<style scoped lang="scss">
.todo-item {
    margin-bottom: 56px;
}
textarea {
    margin-bottom: 24px;
}
</style>
