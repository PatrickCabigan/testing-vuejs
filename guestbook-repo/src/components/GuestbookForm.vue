<template>
  <div>
    <input v-model="name" placeholder="Traveler Name" />
    <textarea v-model="message" placeholder="Write your message..."></textarea>
    <button @click="submit" class="genshin-btn">POST TO LOG</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const emit = defineEmits(['add-entry']);

const name = ref('');
const message = ref('');

const submit = () => {
  if (name.value && message.value) {
    emit('add-entry', {
      id: Date.now(),
      name: name.value,
      text: message.value,
      date: new Date().toLocaleDateString()
    });
    name.value = '';
    message.value = '';
  }
};
</script>