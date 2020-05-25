<template>
  <div>
    <div class="modal" :class="{'is-active': isOpen}">
      <div class="modal-background"></div>
      <div class="modal-card">
        <header class="modal-card-head">
          <p class="modal-card-title">Todo 作成</p>
          <button @click="close" class="delete" aria-label="close"></button>
        </header>
        <section class="modal-card-body">
          <slot />
        </section>
      </div>
    </div>
    <div class="buttons">
      <button @click="isOpen = true" class="button is-info">Create</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false
    };
  },
  watch: {
    close(isClose) {
      if (isClose && this.isOpen) {
        this.isOpen = false;
      }
    }
  },
  methods: {
    close() {
      this.isOpen = false;
    }
  }
};
</script>

<style scoped lang="scss">
.button {
  text-align: center;
  margin: 0 auto;
}
.buttons {
    margin: 40px 0 32px;
}
</style>