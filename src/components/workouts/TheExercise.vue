<template>
  <base-card mode="cardExer" class="flex">
    <p>
      <strong>Core exercise: </strong> {{ title }}
    </p>
    <p><strong>Sets: </strong> {{ sets }}</p>
    <p><strong>Series: </strong> {{ series }}</p>
   
  </base-card>
</template>

<script>
export default {

  props: ["title", "sets", "series"],
};
</script>

<style scoped>
.flex {
  display: flex;
  flex-direction: row;
}
</style>
