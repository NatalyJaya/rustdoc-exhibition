<script setup lang="ts">
// Temporary stand-in for diagrams/components that still need to be built.
defineProps<{ label?: string; hint?: string; click?: number; full?: boolean }>()
</script>

<template>
  <div :class="['ph', { 'ph-full': full }]">
    <span class="ph-eyebrow">PLACEHOLDER</span>
    <p class="ph-label">{{ label ?? 'Diagram / component' }}</p>
    <p v-if="hint" class="ph-hint">{{ hint }}</p>
    <span v-if="click !== undefined" class="ph-click">click {{ click }}</span>
  </div>
</template>

<style scoped>
.ph {
  box-sizing: border-box;
  height: 100%;
  min-height: 180px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 6px;
  padding: 24px;
  border: 1.5px dashed rgba(59, 77, 104, 0.35);
  border-radius: 12px;
  background: rgba(219, 232, 248, 0.25);
  color: #3b4d68;
  text-align: center;
}

.ph-full {
  position: absolute;
  inset: 40px 48px;
  height: auto;
}

.ph-eyebrow {
  color: #8f8c85;
  font-family: 'Inter', sans-serif;
  font-size: 10px;
  font-weight: 700;
  letter-spacing: 0.18em;
}

.ph-label {
  margin: 0;
  font-family: 'Google Sans Flex', sans-serif;
  font-size: 18px;
  font-weight: 650;
}

.ph-hint {
  margin: 0;
  max-width: 36ch;
  color: #8f8c85;
  font-family: 'Inter', sans-serif;
  font-size: 12px;
  line-height: 1.4;
}

.ph-click {
  margin-top: 6px;
  padding: 2px 8px;
  border-radius: 999px;
  background: #dbe8f8;
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
}
</style>
