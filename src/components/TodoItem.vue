<template>
    <article class="message">
      <div class="message-header">
        <p>{{ title }}</p>
        <button class="delete" aria-label="delete"></button>
      </div>
      <div class="message-body">
          {{ description }}
      </div>
    </article>
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
        },
    }
}
</script>
