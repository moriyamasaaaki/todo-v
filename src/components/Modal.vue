<template>
  <div>
    <div class="buttons">
      <button @click="isOpen = true" class="button is-info">Create</button>
    </div>
    <div class="modal" :class="{'is-active': isOpen}">
      <div class="modal-background"></div>
      <div class="modal-card">
        <header class="modal-card-head">
          <p class="modal-card-title">Modal title</p>
          <button @click="isOpen = false" class="delete" aria-label="close"></button>
        </header>
        <section class="modal-card-body">
        <slot />
        </section>
        <footer class="modal-card-foot">
          <button @click="createTodo" type="button" class="button is-success">作成</button>
          <button @click="isOpen = false" class="button">Cancel</button>
        </footer>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false
    }
  },
    methods: {
    createTodo() {
      console.log(this.form)
    }
  }
};
</script>

<style scoped lang="scss">
.button {
  text-align: center;
  margin: 0 auto;
}
</style>