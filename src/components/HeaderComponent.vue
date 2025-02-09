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
}

function toggleHamburgeMenu() {
  hamburgerMenuStatus.value = !hamburgerMenuStatus.value
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
        <a href="/"><span class="blue">D</span>ooin</a>
        <a :href="menu.href" v-for="menu in menuData" v-if="!isMobile">{{ menu.name }}</a>
      </nav>
      <Button name="Get started" v-if="!isMobile"></Button>
      <button v-if="isMobile" :class="['hamburger-button']" @click="toggleHamburgeMenu">
        <HamburgerIcon />
      </button>
    </div>
    <div
      :class="{
        row: true,
        'hamburger-menu': true,
        'show-menu': hamburgerMenuStatus,
        'hide-menu': !hamburgerMenuStatus,
      }"
      v-if="isMobile"
    >
      <nav :class="['flex']">
        <a :href="menu.href" v-for="menu in menuData" :class="['row']">{{ menu.name }}</a>
      </nav>
    </div>
  </header>
</template>

<style scoped lang="scss">
@use './../styles/variables' as variables;
header {
  border-bottom: 1px solid variables.$primary-grey;
  padding: 10px 0 10px 0;
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
        color: variables.$primary-black;
        transition: 0.2s ease;
        font-weight: 400;
        &:first-child {
          font-size: 16px;
          font-weight: 600;
        }
        &:hover,
        span {
          transition: 0.2s ease;
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
  position: relative;
  nav {
    flex-direction: column;
    align-items: center;
    a {
      padding: 32px 0px;
      border-bottom: 1px solid variables.$primary-grey;
      text-align: center;
      text-transform: capitalize;
      &:last-child {
        border: none;
      }
    }
  }
}

.show-menu {
  animation: show-menu-animation 0.5s forwards;
}

.hide-menu {
  animation: hide-menu-animation 0.5s forwards;
}

@keyframes show-menu-animation {
  0% {
    top: -1000px;
  }
  100% {
    top: 0px;
  }
}

@keyframes hide-menu-animation {
  0% {
    top: 0px;
  }
  100% {
    top: -1000px;
    display: none;
  }
}

@media (max-width: 1000px) {
  header {
    padding: 10px 0;
    border: none;
  }
}
</style>
