<script setup lang="ts">
import WelcomeItem from './WelcomeItem.vue'
import { RouterLink, RouterView } from 'vue-router'

// import DocumentationIcon from './icons/IconDocumentation.vue'
// import ToolingIcon from './icons/IconTooling.vue'
// import EcosystemIcon from './icons/IconEcosystem.vue'
// import CommunityIcon from './icons/IconCommunity.vue'
// import SupportIcon from './icons/IconSupport.vue'

import { ref, onMounted } from 'vue'

const items = ref([]) // Define `items` as a reactive variable

onMounted(() => {
  fetch('./portfolio.json')
    .then((response) => response.json())
    .then((data) => {
      console.log('loading all projects')
      console.log(data)
      items.value = data
    })
    .catch((error) => console.error('Error fetching data:', error))
})
</script>

<template>
  <div></div>

  <li v-for="item in items" :key="item.id">
    <router-link :to="`/portfolio/${item.id}`">
      <h2>{{ item.title }}</h2>
      <p>{{ item.description }}</p>
      <img :src="item.img.path" :alt="item.img.alt" />
    </router-link>
  </li>
</template>

<style scoped>
a {
  font-weight: 700;
}
</style>
