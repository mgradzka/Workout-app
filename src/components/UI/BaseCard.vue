<template>
  <div :class="mode">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: ['mode']
}
</script>

<style scoped>
div {
  background-color: rgb(77, 77, 77);
  padding: 1.5rem;
  margin: 2rem auto;
  max-width: 40rem;
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.cardExer {
  /* border: 1px solid rgb(228, 228, 228); */
  background-color: rgb(97, 97, 97);
  margin: 0;
  padding: 1rem
}
</style>
