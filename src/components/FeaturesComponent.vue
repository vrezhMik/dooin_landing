<script setup>
import { ref } from 'vue'

const selectedIndex = ref(0)
</script>

<template>
  <div class="features">
    <div class="features-info">
      <div class="features-info--title">
        <p>Features</p>
      </div>
      <div class="features-info--description">
        <h2>What Makes Dooin Special</h2>
      </div>
      <div class="features-info--menu flex">
        <button @click="selectedIndex = 0">button1</button>
        <button @click="selectedIndex = 1">button2</button>
        <button @click="selectedIndex = 2">button3</button>
        <button @click="selectedIndex = 3">button4</button>
        <button @click="selectedIndex = 4">button5</button>
      </div>
    </div>

    <div class="features-block flex" v-if="selectedIndex === 0">
      <div class="features-block--image">
        <img src="./../assets/block.webp" alt="" />
      </div>
      <div class="features-block--content flex">
        <div class="features-block--content-title">
          <h3>Peer-to-Peer Connections</h3>
        </div>
        <div class="features-block--content-description">
          <p>Directly connect with people who can help you—no middlemen.</p>
        </div>
      </div>
    </div>

    <div class="features-block flex" v-if="selectedIndex === 1">
      <div class="features-block--image">
        <img src="./../assets/block.webp" alt="" />
      </div>
      <div class="features-block--content flex">
        <div class="features-block--content-title">
          <h3>Real Reviews, More Trust</h3>
        </div>
        <div class="features-block--content-description">
          <p>Check real reviews from others and feel confident in your decision.</p>
        </div>
      </div>
    </div>

    <div class="features-block flex" v-if="selectedIndex === 2">
      <div class="features-block--image">
        <img src="./../assets/block.webp" alt="" />
      </div>
      <div class="features-block--content flex">
        <div class="features-block--content-title">
          <h3>Quick and Nearby</h3>
        </div>
        <div class="features-block--content-description">
          <p>Post your task and find the best match for help right in your area.</p>
        </div>
      </div>
    </div>

    <div class="features-block flex" v-if="selectedIndex === 3">
      <div class="features-block--image">
        <img src="./../assets/block.webp" alt="" />
      </div>
      <div class="features-block--content flex">
        <div class="features-block--content-title">
          <h3>Set Up in Seconds</h3>
        </div>
        <div class="features-block--content-description">
          <p>Register and get started in just 3 clicks, it is that easy.</p>
        </div>
      </div>
    </div>

    <div class="features-block flex" v-if="selectedIndex === 4">
      <div class="features-block--image">
        <img src="./../assets/block.webp" alt="" />
      </div>
      <div class="features-block--content flex">
        <div class="features-block--content-title">
          <h3>No Hidden Fees</h3>
        </div>
        <div class="features-block--content-description">
          <p>Use our platform for free - no subscriptions, no commissions.</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
@use './../styles/variables' as variables;
.features {
  margin-top: 100px;
  margin-bottom: 100px;
  &-info {
    max-width: 50%;
    margin: 0 auto;
    text-align: center;
    color: variables.$text-secondary;
    &--title {
      p {
        text-transform: uppercase;
        font-size: 0.8rem;
        font-weight: 400;
      }
      margin-bottom: 1rem;
    }
    &--description {
      h2 {
        font-weight: 500;
        font-size: 2.25rem;
      }
      margin-bottom: 2.4rem;
    }
    &--menu {
      column-gap: 0.8rem;
      justify-content: center;
      align-items: center;
      margin-bottom: 64px;
      button {
        font-size: 0.875rem;
        color: variables.$text-secondary;
        border: 1px solid transparent;
        padding-left: 0.5rem;
        padding-right: 0.5rem;
        padding-top: 0.563rem;
        padding-bottom: 0.563rem;
        background-color: variables.$text-invert;
        border-radius: 15px;
        text-transform: capitalize;
        &:hover {
          border: 1px solid variables.$primary-blue;
          color: variables.$primary-blue;
        }
      }
    }
  }
  &-block {
    background-color: variables.$text-invert;
    max-height: 550px;
    padding: 32px;
    column-gap: 2.4rem;
    border-radius: 30px;
    overflow: hidden;
    &--image {
      max-width: 480px;
      height: 100%;
      img {
        height: 100%;
        border-radius: 30px;
        width: 100%;
      }
    }
    &--content {
      flex-direction: column;
      justify-content: center;
      row-gap: 0.8rem;
      &-title {
        h3 {
          font-size: 2.25rem;
          font-weight: 500;
        }
      }
      &-description {
        font-size: 1rem;
        font-weight: 200;
      }
    }
  }
}
</style>
