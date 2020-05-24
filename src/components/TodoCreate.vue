<template>
  <modal>
    <form action>
      <div class="field">
        <label class="label">タイトル</label>
        <div class="control">
          <input v-model="form.title" class="input" type="text" placeholder="Text input" />
        </div>
      </div>
      <div>
        <label class="label">内容</label>
        <div class="control">
          <textarea v-model="form.description" class="textarea" placeholder="10 lines of textarea" rows="10"></textarea>
        </div>
      </div>
        <button @click="submitForm" type="button" class="button is-success">作成</button>
        <button @click="isOpen = false" class="button">Cancel</button>
    </form>
  </modal>
</template>

<script>
import Modal from "@/components/Modal";
export default {
  components: {
    Modal
  },
  data() {
    return {
      form: {
        title: "",
        description: ""
      }
    };
  },
methods: {
    submitForm() {
      this.$emit('formSubmitted', {...this.form})
      this.resetForm()
    },
    resetForm() {
      this.form.title = ''
      this.form.description = ''
    }
  }
};
</script>