<template>
<modal>
        <form action>
          <div class="field">
            <label class="label">タイトル</label>
            <div class="control">
              <input v-model="form.title" class="input" type="text" placeholder="Text input" />
            </div>
          </div>
          <div class="field">
            <label class="label">内容</label>
            <div class="control">
              <input v-model="form.description" class="input" type="text" placeholder="Text input" />
            </div>
          </div>
        </form>
    </modal>
</template>

<script>
import Modal from '@/components/Modal'
export default {
  components: {
    Modal
  },
  data() {
    return {
      form: {
        title: '',
        description: ''
      }
    }
  },
}
</script>