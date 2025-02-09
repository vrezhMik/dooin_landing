<script setup></script>

<template>
  <div class="usage">
    <div class="usage-info">
      <div class="usage-info-title">
        <p>this is how it works</p>
      </div>
      <div class="usage-info--description">
        <h2>Add title for this section</h2>
      </div>
    </div>
    <div class="usage-block flex">
      <div class="usage-block--image">
        <img src="./../assets/block2.webp" alt="" />
      </div>
      <div class="usage-block--content flex">
        <div class="usage-block--content-title">
          <h3>Schnelle Reinigung Deiner Wohnung</h3>
        </div>
        <div class="usage-block--content-description">
          <p>
            No time to clean your apartment? Post the task and quickly find someone who can help you
            clean – whether it’s a quick sweep or a thorough cleaning.
          </p>
        </div>
      </div>
    </div>
    <div class="usage-block flex image-left">
      <div class="usage-block--image">
        <img src="./../assets/block2.webp" alt="" />
      </div>
      <div class="usage-block--content flex">
        <div class="usage-block--content-title">
          <h3>Einkäufe Erledigen lassen</h3>
        </div>
        <div class="usage-block--content-description">
          <p>
            UNeed groceries or other items urgently but don’t have time? Have a tasker do your
            shopping and bring the goods directly to your door."
          </p>
        </div>
      </div>
    </div>
    <div class="usage-block flex">
      <div class="usage-block--image">
        <img src="./../assets/block2.webp" alt="" />
      </div>
      <div class="usage-block--content flex">
        <div class="usage-block--content-title">
          <h3>Freiwillige Hilfe für die Nachbarschaft</h3>
        </div>
        <div class="usage-block--content-description">
          <p>
            Organize volunteer help for neighbors – such as cleaning out, shopping for seniors, or
            supporting refugee initiatives."
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use './../styles/variables' as variables;
.usage {
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
          font-size: 1.5rem;
          font-weight: 500;
        }
      }
      &-description {
        font-size: 1rem;
        font-weight: 400;
      }
    }
  }
}

.image-left {
  flex-direction: row-reverse;
}
</style>
