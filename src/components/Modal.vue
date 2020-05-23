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
          Google Chrome アプリのようなある環境では、Content Security Policy (CSP) を強制し、そして式を評価するために new Function() の使用を禁止しています。テンプレートのコンパイルは、完全ビルドに依存するため、これらの環境では使用できません。
          一方では、ランタイム限定ビルドでは CSP に準拠しています。 Webpack + vue-loader または Browserify + vueify でランタイム限定ビルドを使用する場合は、テンプレートは CSP 環境でも完璧に動作する render 関数にプリコンパイルされます。
        </section>
        <footer class="modal-card-foot">
          <button class="button is-success">Save changes</button>
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
    };
  }
};
</script>

<style scoped lang="scss">
.button {
    text-align: center;
    margin: 0 auto;
}
</style>