<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { RouterLink, RouterView } from 'vue-router'

const jsonData = ref(null)
interface PortfolioItem {
  id: number
  Title: string
  About: string
}

const items = ref<PortfolioItem[]>([]) // Define items outside onMounted

onMounted(() => {
  fetch('portfolio.json')
    .then((response) => response.json())
    .then((data) => {
      console.log(data)
      jsonData.value = data.portfolio
      items.value = data.portfolio // Update items with JSON data
    })
    .catch((error) => console.error('Error fetching JSON:', error))
})
</script>

<template>
  <div class="item">
    <div class="details" v-for="item in items" :key="item.id">
      <h3>
        <slot>{{ item.Title }}</slot>
      </h3>
      <slot>{{ item.About }}</slot>
    </div>
  </div>
</template>

<style scoped>
.item {
  height: 10rem;
  display: flex;
  position: relative;
}

.details {
  /* flex: 1; */
  display: flex;
  align-items: end;
  /* margin-left: 1rem; */
}

h3 {
  font-size: 1.2rem;
  font-weight: 500;
  color: var(--color-heading);
}

/* @media (min-width: 1024px) {
  .item {
    margin-top: 0;
    padding: 0.4rem 0 1rem calc(var(--section-gap) / 2);
  }

  i {
    top: calc(50% - 25px);
    left: -26px;
    position: absolute;
    border: 1px solid var(--color-border);
    background: var(--color-background);
    border-radius: 8px;
    width: 50px;
    height: 50px;
  }

  .item:before {
    content: ' ';
    border-left: 1px solid var(--color-border);
    position: absolute;
    left: 0;
    bottom: calc(50% + 25px);
    height: calc(50% - 25px);
  }

  .item:after {
    content: ' ';
    border-left: 1px solid var(--color-border);
    position: absolute;
    left: 0;
    top: calc(50% + 25px);
    height: calc(50% - 25px);
  }

  .item:first-of-type:before {
    display: none;
  }

  .item:last-of-type:after {
    display: none;
  }
} */
</style>
