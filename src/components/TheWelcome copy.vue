<script setup lang="ts">
import { ref, onMounted } from 'vue'
import WelcomeItem from './WelcomeItem.vue'
import { RouterLink, RouterView } from 'vue-router'

import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'

const jsonData = ref(null)

onMounted(() => {
  fetch('/portfolio.json')
    .then((response) => response.json())
    .then((data) => {
      console.log(data)
      jsonData.value = data.portfolio
      const items = ref(jsonData) // Attach JSON data to `items`
    })
    .catch((error) => console.error('Error fetching JSON:', error))
})
</script>

<template>
  <div>
    <WelcomeItem>
      <!-- <template #icon>
      <DocumentationIcon />
    </template> -->
      <template #heading><RouterLink to="/about">Portfolio</RouterLink></template>
    </WelcomeItem>

    <WelcomeItem>
      <!-- <template #icon>
      <DocumentationIcon />
    </template> -->
      <template #heading><RouterLink to="/about">Portfolio</RouterLink></template>
    </WelcomeItem>

    <WelcomeItem>
      <!-- <template #icon>
      <DocumentationIcon />
    </template> -->
      <template #heading><RouterLink to="/about">Portfolio</RouterLink></template>
    </WelcomeItem>

    <WelcomeItem>
      <!-- <template #icon>
      <DocumentationIcon />
    </template> -->
      <template #heading><RouterLink to="/about">Portfolio</RouterLink></template>
    </WelcomeItem>

    <WelcomeItem>
      <!-- <template #icon>
      <DocumentationIcon />
    </template> -->
      <template #heading><RouterLink to="/about">Portfolio</RouterLink></template>
    </WelcomeItem>
  </div>
  <div>
    <ul>
      <li v-for="item in items" :key="item.id">
        <h2>{{ item.Title }}</h2>
        <p>{{ item.description }}</p>
      </li>
    </ul>
  </div>
</template>
