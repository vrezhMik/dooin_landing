<script setup>
import { ref } from 'vue'
import PlusIcon from './Icons/PlusIcon.vue'

const openIndexes = ref({})

const toggleAnswer = (index) => {
  openIndexes.value[index] = !openIndexes.value[index]
}
</script>

<template>
  <div class="faq">
    <div class="faq-info">
      <div class="faq-info--title">
        <h2>Häufig gestellte Fragen</h2>
      </div>
    </div>

    <div class="faq-block">
      <div class="row faq-block--question flex">
        <div class="faq-block--question-title">How Does Dooin Work?</div>
        <div class="faq-block--question-button">
          <button @click="toggleAnswer(1)"><PlusIcon /></button>
        </div>
      </div>
      <div class="row faq-block--answer" :class="{ open: openIndexes[1] }">
        <p>
          You can post tasks or look for tasks to help with. Find the right helper and complete the
          task.
        </p>
      </div>
    </div>

    <div class="faq-block">
      <div class="row faq-block--question flex">
        <div class="faq-block--question-title">How Much Does It Cost?</div>
        <div class="faq-block--question-button">
          <button @click="toggleAnswer(2)"><PlusIcon /></button>
        </div>
      </div>
      <div class="row faq-block--answer" :class="{ open: openIndexes[2] }">
        <p>Dooin is free! You only pay for the help you get or give.</p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use './../styles/variables' as variables;

.faq {
  background-image: linear-gradient(180deg, rgba(54, 97, 246, 0.1), #f3f7fb);
  padding: 4.8rem;
  border-radius: 30px;

  &-info {
    max-width: 50%;
    margin: 0 auto;
    text-align: center;
    color: variables.$text-secondary;

    &--title {
      h2 {
        font-weight: 500;
        font-size: 2.25rem;
      }
      margin-bottom: 2.4rem;
    }
  }

  &-block {
    padding: 1.6rem;
    margin-top: 1rem;
    border-radius: 1.6rem;
    border: 1px solid variables.$primary-grey;
    overflow: hidden;

    &--question {
      justify-content: space-between;
      align-items: center;
      display: flex;
      cursor: pointer;

      &-title {
        font-weight: 600;
        font-size: 18px;
      }

      &-button {
        height: 22.6px;
        width: 22.6px;

        button {
          height: 100%;
          width: 100%;
          border: none;
          background: transparent;
          cursor: pointer;

          svg {
            height: 100%;
            width: 100%;
          }
        }
      }
    }

    &--answer {
      max-height: 0;
      overflow: hidden;
      font-size: 1rem;
      font-weight: 200;
      opacity: 0;
      padding-top: 0;
      transition:
        max-height 0.3s ease-out,
        opacity 0.3s ease-out,
        padding-top 0.3s ease-out;
    }

    &--answer.open {
      max-height: 200px;
      opacity: 1;
      padding-top: 20px;
      transition:
        max-height 0.3s ease-in,
        opacity 0.3s ease-in,
        padding-top 0.3s ease-in;
    }
  }
}
</style>
