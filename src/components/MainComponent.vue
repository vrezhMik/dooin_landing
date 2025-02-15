<script setup>
import BannerComponent from './BannerComponent.vue'
import FeaturesComponent from './FeaturesComponent.vue'
import UsageComponent from './UsageComponent.vue'
import FAQComponent from './FAQComponent.vue'
import InstallationComponent from './InstallationComponent.vue'
</script>

<template>
  <main class="sora">
    <BannerComponent />
    <FeaturesComponent />
    <UsageComponent />
    <FAQComponent />
    <InstallationComponent />
  </main>
</template>

<style scoped lang="scss">
main {
  margin-top: 50px;
}
</style>
