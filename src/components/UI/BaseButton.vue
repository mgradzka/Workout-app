<template>
  <button :class="mode">
    <slot></slot>
  </button>
</template>

<script>
export default {
    props: ['mode']
}
</script>

<style scoped>
button {
    
  width: fit-content;
  font-family: inherit;
  border: 1px solid greenyellow;
  background-color: greenyellow;
  padding: 0.75rem 1.5rem;
  cursor: pointer;
}

button:hover {
    background-color: rgb(144, 215, 37);
    border: 1px solid rgb(144, 215, 37);
}

.transparent{
    background-color: transparent;
    border: 1px solid transparent;
    color: rgb(208, 208, 208)
}
.transparent:hover {
     background-color: rgb(33, 40, 22);
      border: 1px solid transparent;
}
</style>
