<script setup lang="ts">
defineProps<{
  msg: string
}>()
import { RouterLink, RouterView } from 'vue-router'

import HelloWorldItem from './HelloWorldItem.vue'
import Logo from './icons/Logo.vue'
</script>

<template>
  <div class="greetings">
    <!-- <HelloWorldItem>
      <template #icon>
        <Logo />
      </template>
    </HelloWorldItem> -->

    <!-- <h1 class="heading">{{ msg }}</h1> -->
    <h1 class="heading">
      <RouterLink to="/">max <i>is</i> well</RouterLink>
    </h1>
    <!-- <h3>designing with intent</h3> -->
  </div>
</template>

<style scoped>
a {
  /* height: 100%; */
  font-weight: 700;
}

i {
  font-style: italic;
  font-weight: 700;
}

/* .greetings {
  display: flex;
  align-items: baseline;
} */
</style>
