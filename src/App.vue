<template>
  <Card>
    <template #front>
      <h1 class="front__title">Поздравляем со свадьбой!</h1>
      <p class="front__text">Желаем счастливой семейной жизни <br /> От всей души Вова и Кирилл</p>
    </template>
    <template #back>
      <h1 class="back__title">Сертификат</h1>
      <p class="back__text">На разработку лендинга под ключ для Валерия и Любы</p>
      <img class="back__naiveui" src="@/assets/img/image%206.png" alt="naiveui" />
      <img class="back__vuejs" src="@/assets/img/image%204.png" alt="vue.js" />
      <img class="back__married-people" src="@/assets/img/image%205.png" alt="married people" />
      <img class="back__dev" src="@/assets/img/image%202.png" alt="dev" />
    </template>
  </Card>
</template>

<script setup>
import { onBeforeMount } from 'vue';

import Card from '@/components/Card.vue';

const DEFAULT_WIDTH = 1200;

const resize = () => document.documentElement.style.fontSize = window.innerWidth / DEFAULT_WIDTH * 10 + 'px';

window.addEventListener('resize', resize);

onBeforeMount(resize)
</script>

<style scoped lang="scss">
@mixin default-text($top: 50%, $left: 50%) {
  position: absolute;
  top: $top;
  left: $left;
  transform: translate(-50%, -50%);
  white-space: nowrap;
}

.front {
  &__title {
    @include default-text;
  }

  &__text {
    position: absolute;
    bottom: 3.2rem;
    left: 50%;
    transform: translateX(-50%);
    text-align: center;
  }
}

.back {
  &__title {
    @include default-text(25%);
  }

  &__text {
    @include default-text;
  }

  &__naiveui {
    position: absolute;
    top: 1rem;
    left: 1rem;
    height: 10rem;
  }

  &__vuejs {
    position: absolute;
    top: 1rem;
    right: 1rem;
    width: 10rem;
  }

  &__married-people {
    position: absolute;
    bottom: 1rem;
    right: 1rem;
    width: 20rem;
  }

  &__dev {
    position: absolute;
    bottom: 1rem;
    left: 1rem;
    width: 25rem;
  }
}
</style>
