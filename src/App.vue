<template>
  <Card>
    <template #front>
      <h1 class="front__title">Поздравляем со свадьбой!</h1>
      <p class="front__text">Желаем счастливой семейной жизни <br /> От всей души Вова и Кирилл</p>
    </template>
    <template #back>
      <h1>back</h1>
    </template>
  </Card>
</template>

<script setup>
import Card from '@/components/Card.vue';
</script>

<style scoped lang="scss">
.front__title {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  white-space: nowrap;
}

.front__text {
  position: absolute;
  bottom: 3.2rem;
  left: 50%;
  transform: translateX(-50%);
  text-align: center;
}
</style>
