<script setup></script>
<template>
  <div class="about-author">
    <img class="about-author__photo" src="../assets/img/author-photo.jpg" alt="author photo" />
    <h3 class="about-author__name">Kate Willems</h3>
    <p class="about-author__career">Food & cooking bloger</p>
    <p class="about-author__description">
      Hi, I'm Sonia. Cooking is the way I express my creative side to the world. Welcome to my
      Kitchen Corner on…
    </p>
    <a class="about-author__link">Continue Reading</a>
  </div>
</template>

<style lang="scss">
.about-author {
  text-align: center;
  box-shadow: 0px 2px 6px rgba(0, 0, 0, 0.1);

  &__photo {
    width: 270px;
    height: 180px;
    margin-bottom: 20px;
  }

  &__name {
    font-weight: 700;
    font-size: 16px;
    line-height: 21px;
    text-align: center;
    margin-bottom: 4px;
  }

  &__career {
    font-style: italic;
    font-size: 14px;
    font-weight: 400;
    line-height: 19px;
    text-align: center;
    color: #b1b1b1;
    margin-bottom: 14px;
  }

  &__description {
    font-size: 14px;
    line-height: 24px;
    text-align: center;
    color: #666666;
    margin-bottom: 14px;
  }

  &__link {
    font-family: 'PT Serif';
    font-style: normal;
    font-weight: 400;
    font-size: 12px;
    line-height: 16px;
    text-transform: uppercase;
    color: var(--gold-color);
    padding: 12px 0;
    border-top: 1px solid #e5e5e5;
    display: block;
    cursor: pointer;
  }
}
</style>
