<script setup>
import BannerComponent from './BannerComponent.vue'
import FeaturesComponent from './FeaturesComponent.vue'
import UsageComponent from './UsageComponent.vue'
</script>

<template>
  <main class="container sora">
    <BannerComponent />
    <FeaturesComponent />
    <UsageComponent />
  </main>
</template>

<style scoped lang="scss">
main {
  margin-top: 50px;
}
</style>
