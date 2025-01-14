<script setup>
const props = defineProps(['name'])
</script>

<template>
  <button>{{ props.name }}</button>
</template>

<style scoped lang="scss">
@import './../styles/variables';

button {
  padding: 1rem 1.2rem;
  font-size: 0.9rem;
  border: 1px solid $primary-grey;
  border-radius: 50px;
  color: $primary-black;
  transition: 0.2s ease;
  &:hover {
    background-color: $primary-orange;
    color: $primary-white;
    transition: 0.2s ease;
  }
}
</style>
