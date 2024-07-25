<template>
  <div class="container">
    <div class="card" :class="{ flipped }" @click="toggleFlipped">
      <div class="card__front">
        <div class="card__content">
          <slot name="front" />
        </div>
      </div>
      <div class="card__back">
        <div class="card__content">
          <slot name="back" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const flipped = ref(false);

const toggleFlipped = () => flipped.value = !flipped.value
</script>

<style scoped lang="scss">
.container {
  position: relative;
  width: 100rem;
  height: 60rem;
}

.card {
  position: absolute;
  width: 100%;
  height: 100%;
  transform-style: preserve-3d;
  transition: all 500ms ease-in-out;

  &__front,
  &__back {
    position: absolute;
    width: 100%;
    height: 100%;
    padding: 3.2rem;
    backface-visibility: hidden;
    background: var(--color-white);
  }

  &__back {
    transform: rotateY(180deg);
  }

  &__content {
    position: relative;
    width: 100%;
    height: 100%;
    border: 1rem solid var(--color-primary);
  }

  &.flipped {
    transform: rotateY(180deg);
  }
}
</style>
