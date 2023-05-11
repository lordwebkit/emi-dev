<script setup>
import { defineProps } from 'vue'
const props = defineProps(['id', 'theme', 'name', 'date', 'author'])
</script>
<template>
  <div class="featured-post">
    <img class="featured-post__img" :src="`src/assets/img/featured-post-${id}.jpg`" alt="" />
    <p class="featured-post__theme">
      {{ props.theme }}
    </p>
    <h3 class="featured-post__name">{{ props.name }}</h3>
    <div class="featured-post__info">
      <p class="featured-post__date">{{ props.date }}</p>
      <p class="featured-post__author">
        <span class="featured-post__author--gray">By</span> {{ props.author }}
      </p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.featured-post {
  margin-top: 20px;
  width: 100%;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
  text-align: center;
  padding-bottom: 10px;

  &__img {
    width: 270px;
    height: 160px;
  }

  &__theme {
    font-size: 12px;
    line-height: 16px;
    text-transform: uppercase;
    color: var(--gold-color);
    margin-top: 8px;
    margin-bottom: 4px;
  }

  &__name {
    font-size: 18px;
    line-height: 26px;
    text-align: center;
    margin-bottom: 10px;
  }

  &__info {
    display: flex;
    justify-content: center;
    font-size: 12px;
    line-height: 16px;
    margin-bottom: 14px;
    color: #666666;
  }

  &__author--gray {
    color: var(--gray-light-color);
    margin-left: 10px;
  }
}
</style>
