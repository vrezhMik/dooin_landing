<script setup>
import Button from './ButtonComponent.vue'
</script>

<template>
  <header :class="['container', 'flex', 'sora']">
    <nav :class="['header-menu', 'flex']">
      <a href="/"><span>D</span>ooin</a>
      <a href="/">home</a>
      <a href="#product">product</a>
      <a href="#about">about</a>
    </nav>
    <div :class="['']">
      <Button name="Get Started"></Button>
    </div>
  </header>
</template>

<style scoped lang="scss">
@import './../styles/variables';
header {
  border-bottom: 1px solid $primary-grey;
  height: 50px;
  padding: 30px 0;
  align-items: center;
  position: sticky;
  justify-content: space-between;
  top: 0;
  .header-menu {
    width: 30%;
    column-gap: 30px;
    a {
      font-size: 14px;
      color: $primary-black;
      transition: 0.2s ease;
      font-weight: 400;
      &:first-child {
        font-size: 16px;
        font-weight: 600;
      }
      &:hover,
      span {
        transition: 0.2s ease;
        color: $primary-blue;
      }
    }
  }
}
</style>
