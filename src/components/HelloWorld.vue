<script setup lang="ts">
defineProps<{
  msg: string
}>()
import HelloWorldItem from './HelloWorldItem.vue'
import Logo from './icons/Logo.vue'
</script>

<template>
  <div class="greetings">
    <HelloWorldItem>
      <template #icon>
        <Logo />
      </template>
    </HelloWorldItem>

    <h1 class="green">{{ msg }}</h1>
    <!-- <h3>designing with intent</h3> -->
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2rem;
  position: relative;
  /* top: -10px; */
  width: 100%;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
  width: 100%;
}
.greetings {
  display: flex;
  justify-content: center;
  align-items: center;
}

/* @media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
} */
</style>
