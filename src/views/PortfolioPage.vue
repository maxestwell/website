<script setup>
import { ref, onMounted } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const item = ref(null)

onMounted(() => {
  //now we are nested need to go up a directory to get json
  fetch('../portfolio.json')
    .then((response) => response.json())
    .then((data) => {
      console.log('loading single project')

      item.value = data.find((i) => i.id === Number(route.params.id))
    })
    .catch((error) => console.error('Error fetching item data:', error))
})
</script>

<template>
  <div v-if="item">
    <h1>{{ item.title }}</h1>
    <p>{{ item.description }}</p>
    <img :src="item.img.path" :alt="item.img.alt" />
  </div>
  <div v-else>
    <p>Loading...</p>
  </div>
</template>
