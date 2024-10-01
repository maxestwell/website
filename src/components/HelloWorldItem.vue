<template>
  <div class="item">
    <i>
      <slot name="icon"></slot>
    </i>
  </div>
</template>

<style scoped>
.item {
  display: flex;
  position: relative;
}

i {
  display: flex;
  /* place-items: center; */
  place-content: center;
  width: 50%;
  height: 50px;

  color: var(--color-text);
}
</style>
