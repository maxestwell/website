<script setup lang="ts">
import WelcomeItem from './WelcomeItem.vue'
import { RouterLink, RouterView } from 'vue-router'

import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
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
</template>
