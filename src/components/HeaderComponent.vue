<script setup>
import Button from './ButtonComponent.vue'
import HamburgerIcon from './Icons/HamburgerIcon.vue'
import { ref, onMounted, onUnmounted } from 'vue'

const menuData = [
  { href: '/', name: 'home' },
  { href: '#product', name: 'product' },
  { href: '#about', name: 'about' },
]

const isMobile = ref(window.innerWidth < 1000)
const hamburgerMenuStatus = ref(false)

const updateWidth = () => {
  isMobile.value = window.innerWidth < 1000
  console.log(isMobile.value)
}

function toggleHamburgeMenu() {
  hamburgerMenuStatus.value = !hamburgerMenuStatus.value
  console.log(hamburgerMenuStatus.value)
}

onMounted(() => {
  window.addEventListener('resize', updateWidth)
})

onUnmounted(() => {
  window.removeEventListener('resize', updateWidth)
})
</script>

<template>
  <header :class="['container', 'sora']">
    <div :class="['row', 'flex']">
      <nav :class="['header-menu', 'flex']">
        <a href="/"><span>D</span>ooin</a>
        <a :href="menu.href" v-for="menu in menuData" v-if="!isMobile">{{ menu.name }}</a>
      </nav>
      <Button name="Get Started" v-if="!isMobile"></Button>
      <button v-if="isMobile" :class="['hamburger-button']" @click="toggleHamburgeMenu">
        <HamburgerIcon />
      </button>
    </div>
    <div :class="['row', 'hamburger-menu']" v-if="hamburgerMenuStatus">
      <nav :class="['flex']">
        <a :href="menu.href" v-for="menu in menuData" :class="['row']">{{ menu.name }}</a>
      </nav>
    </div>
  </header>
</template>

<style scoped lang="scss">
@import './../styles/variables';
header {
  border-bottom: 1px solid $primary-grey;
  padding: 30px 0 10px 0;
  position: sticky;
  top: 0;
  div {
    justify-content: space-between;
    align-items: center;

    .header-menu {
      align-items: center;
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
}

.hamburger-button {
  width: 30px;
  height: 30px;
}

.hamburger-menu {
  nav {
    flex-direction: column;
    align-items: center;
    a {
      padding: 32px 0px;
      border-bottom: 1px solid $primary-grey;
      text-align: center;
      text-transform: capitalize;
      &:last-child {
        border: none;
      }
    }
  }
}

@media (max-width: 1000px) {
  header {
    padding: 10px 0;
  }
}
</style>
