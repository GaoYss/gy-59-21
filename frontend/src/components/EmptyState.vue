<script setup>
defineProps({
  title: {
    type: String,
    required: true
  },
  description: {
    type: String,
    default: ''
  },
  actionText: {
    type: String,
    default: ''
  }
})

const emit = defineEmits(['action'])
</script>

<template>
  <div class="empty-state">
    <strong>{{ title }}</strong>
    <span v-if="description">{{ description }}</span>
    <button v-if="actionText" class="primary-button" type="button" @click="emit('action')">
      {{ actionText }}
    </button>
  </div>
</template>
