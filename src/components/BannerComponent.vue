<script setup>
import ButtonComponent from './ButtonComponent.vue'
import ThemeButton from './ThemeButton.vue'
</script>

<template>
  <div class="banner">
    <div class="row">
      <h1 class="banner-title">Say bye to <span class="blue">chaos.</span></h1>
    </div>
    <div class="row banner-description">
      <p>
        Amet minim mollit non deserunt ullamco est sit aliqua dolor do amet sint. Velit officia
        consequat duis enim velit mollit.
      </p>
    </div>
    <div class="row flex banner-buttons">
      <ThemeButton name="Get started" />
      <ButtonComponent name="Get demo" />
    </div>
    <div></div>
  </div>
</template>

<style scoped lang="scss">
.banner {
  background: hsla(226, 63%, 95%, 1);
  background: linear-gradient(270deg, hsla(226, 63%, 95%, 1) 0%, hsla(0, 0%, 100%, 1) 100%);
  background: -moz-linear-gradient(270deg, hsla(226, 63%, 95%, 1) 0%, hsla(0, 0%, 100%, 1) 100%);
  background: -webkit-linear-gradient(270deg, hsla(226, 63%, 95%, 1) 0%, hsla(0, 0%, 100%, 1) 100%);
  padding: 76px 76px 32px 76px;
  border-radius: 30px;
  &-title {
    text-align: center;
    font-size: 3.8rem;
    font-weight: 500;
    margin-bottom: 16px;
  }
  &-description {
    font-weight: 300;
    text-align: center;
    width: 70%;
    margin: 0 auto;
    margin-bottom: 32px;
  }
  &-buttons {
    justify-content: center;
    column-gap: 12px;
  }
}
</style>
