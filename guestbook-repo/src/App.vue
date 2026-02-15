<template>
  <div class="genshin-container">
    <h1 style="text-align: center; color: var(--genshin-gold);">✦ GUESTBOOK ✦</h1>
    
    <GuestbookForm @add-entry="addNewEntry" />
    
    <hr style="border: 0; height: 1px; background: var(--genshin-gold); margin: 25px 0;" />
    
    <GuestbookList :entries="messages" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import GuestbookForm from './components/GuestbookForm.vue';
import GuestbookList from './components/GuestbookList.vue';

const messages = ref([
  { id: 1, name: 'Paimon', text: 'Is there any Sticky Honey Roast here?', date: '2024-05-20' }
]);

const addNewEntry = (entry) => {
  messages.value.unshift(entry);
};
</script>