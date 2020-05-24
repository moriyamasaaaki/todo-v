<template>
  <modal ref="modal">
    <form action>
      <div class="field">
        <label class="label">タイトル</label>
        <div class="control">
          <input v-model="form.title" class="input" type="text" placeholder="Text input" />
        </div>
        <p class="help is-danger">{{ formError }}</p>
      </div>
      <div>
        <label class="label">内容</label>
        <div class="control">
          <textarea
            v-model="form.description"
            class="textarea"
            placeholder="10 lines of textarea"
            rows="10"
          ></textarea>
        </div>
        <p class="help is-danger">{{ formError }}</p>
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
      },
      formError: ""
    };
  },
  computed: {
    isFormValid() {
      return this.form.title.length > 8 && this.form.description.length > 10
        ? true
        : false;
    },
    modal() {
      return this.$refs.modal;
    }
  },
  methods: {
    submitForm() {
      if (this.isFormValid) {
        this.formError = "";
        this.$emit("formSubmitted", { ...this.form });
        this.modal.close();
        this.resetForm();
      } else {
        this.formError = "入力した値が不正です。";
      }
    },
    resetForm() {
      this.form.title = "";
      this.form.description = "";
    }
  }
};
</script>