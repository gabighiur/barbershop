<script setup>
import { ref } from 'vue'

const isAnimating = ref(false)

function startAnimation() {
  isAnimating.value = true
}

function stopAnimation() {
  isAnimating.value = false
}
</script>

<template>
  <button class="icon-button relative" @mouseenter="startAnimation" @mouseleave="stopAnimation">
    <div class="light-effect absolute left-0 top-0 h-full w-full rounded-full bg-amber-100 opacity-0" />
    <div class="background-effect absolute left-0 top-0 h-full w-full rounded-full bg-amber-100" />
    <div class="icon-container">
      <div i-carbon:phone-filled class="icon animate-pulse text-cyan-950" />
    </div>
  </button>
</template>

  <style scoped>
  .icon-button {
  @apply rounded-full;
  outline: none;
  border: none;
  cursor: pointer;
  padding: 10px;
  overflow: hidden;
  position: relative;
  transition: transform 0.3s ease;
}

.light-effect {
  animation: lightEffectAnimation 2s infinite ease-in-out;
}

.background-effect {
  opacity: 0.7;
}

@keyframes lightEffectAnimation {
  0% {
    transform: scale(0);
    opacity: 0.7;
  }
  50% {
    transform: scale(1);
    opacity: 0.3;
  }
  100% {
    transform: scale(2);
    opacity: 0;
  }
}

.icon-container {
  display: flex;
  align-items: center;
}

.icon {
  font-size: 2rem;
}

.icon-button:hover {
  transform: scale(1.1) rotate(5deg);
}
</style>
