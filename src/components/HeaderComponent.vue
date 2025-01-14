<script setup>
import Button from './ButtonComponent.vue'
import HamburgerIcon from './Icons/HamburgerIcon.vue'
import { ref, onMounted, onUnmounted } from 'vue'

const isMobile = ref(window.innerWidth < 1000)

const updateWidth = () => {
  isMobile.value = window.innerWidth < 1000
  console.log(isMobile.value)
}

onMounted(() => {
  window.addEventListener('resize', updateWidth)
})

onUnmounted(() => {
  window.removeEventListener('resize', updateWidth)
})
</script>

<template>
  <header :class="['container', 'flex', 'sora']">
    <nav :class="['header-menu', 'flex']">
      <a href="/"><span>D</span>ooin</a>
      <a href="/" v-if="!isMobile">home</a>
      <a href="#product" v-if="!isMobile">product</a>
      <a href="#about" v-if="!isMobile">about</a>
    </nav>
    <div :class="['']">
      <Button name="Get Started" v-if="!isMobile"></Button>
      <button v-if="isMobile" :class="['hamburger']">
        <HamburgerIcon />
      </button>
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

.hamburger {
  width: 30px;
  height: 30px;
}

@media (max-width: 1000px) {
  header {
    padding: 0;
  }
}
</style>
