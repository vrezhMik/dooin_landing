<script></script>
<template>
  <div class="installation">
    <div class="installation-info">
      <div class="installation-info--description">
        <h2>Wie es funktioniert – Nur 3 Klicks!</h2>
      </div>
    </div>
    <div class="installation-steps">
      <div class="installation-steps--block">
        <span>1</span>
        <h2>Sign up in seconds.</h2>
      </div>
      <div class="installation-steps--block">
        <span>2</span>
        <h2>Create or find a task that suits you.</h2>
      </div>
      <div class="installation-steps--block">
        <span>3</span>
        <h2>Connect with the right person – done!</h2>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use './../styles/variables' as variables;

.installation {
  background-color: variables.$background-invert;
  padding: 80px 0;
  &-info {
    max-width: 50%;
    margin: 0 auto;
    text-align: center;
    color: variables.$text-invert;
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
        font-size: 3.3rem;
      }
    }
  }
  &-steps {
    display: flex;
    padding: 50px 30px;
    align-items: center;
    justify-content: space-evenly;
    &--block {
      height: 400px;
      width: 400px;
      border-radius: 30px;
      background-color: variables.$text-invert;
      display: flex;
      align-items: center;
      justify-content: space-evenly;
      padding: 20px;
      column-gap: 30px;
      span {
        font-size: 10rem;
        color: variables.$primary-blue;
      }
      h2 {
        font-size: 2.2rem;
        width: 70%;
      }
    }
  }
}
</style>
