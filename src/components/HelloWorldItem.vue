<template>
  <div class="item">
    <slot name="icon"></slot>
  </div>
</template>

<style scoped>
.item {
  display: flex;
  position: relative;
  padding-right: 1rem;
}

#icon {
  color: var(--color-text);
}
</style>
