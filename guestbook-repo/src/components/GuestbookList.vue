<template>
  <div class="list">
    <div v-for="item in entries" :key="item.id" class="entry">
      <div style="display:flex; justify-content: space-between; color: var(--genshin-gold);">
        <strong>{{ item.name }}</strong>
        <small>{{ item.date }}</small>
      </div>
      <p style="margin: 8px 0 0 0; font-style: italic; opacity: 0.9;">"{{ item.text }}"</p>
    </div>
  </div>
</template>

<script setup>
defineProps(['entries']);
</script>

<style scoped>
.entry {
  background: rgba(255,255,255,0.03);
  padding: 15px;
  margin-bottom: 10px;
  border-left: 3px solid var(--genshin-gold);
}
</style>