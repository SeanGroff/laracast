<template>
  <button @click="$emit('completeTask')">
    x
  </button>
</template>

<script>
export default {};
</script>

<style scoped>
button {
  background-color: limegreen;
  color: white;
}
</style>
