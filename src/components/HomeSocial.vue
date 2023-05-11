<script setup>
import { ref } from 'vue'
const socialList = ref([
  { icon: 'facebook', quantity: '32k', activity: 'likes' },
  { icon: 'pinterest', quantity: '814', activity: 'followers' },
  { icon: 'vimeo', quantity: '165', activity: 'followers' },
  { icon: 'dribble', quantity: '6k', activity: 'followers' },
  { icon: 'twitter', quantity: '130k', activity: 'followers' },
  { icon: 'behance', quantity: '37k', activity: 'followers' },
  { icon: 'instagram', quantity: '854k', activity: 'followers' },
  { icon: 'youtube', quantity: '52k', activity: 'subscribers' },
  { icon: 'google', quantity: '642k', activity: 'followers' }
])
</script>
<template>
  <div class="social">
    <span class="social__item" v-for="social in socialList" :key="social">
      <img class="social__icon" :src="`src/assets/icon/social/${social.icon}.svg`" alt="" />
      <p class="social__quantity">{{ social.quantity }}</p>
      <p class="social__activity">{{ social.activity }}</p>
    </span>
  </div>
</template>

<style lang="scss" scoped>
.social {
  display: flex;
  flex-wrap: wrap;

  &__item {
    width: 88px;
    height: 88px;
    display: flex;
    background-color: #f8f9fa;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-size: 12px;
    line-height: 16px;
    text-align: center;
    color: #999999;
    margin-right: 2px;
    margin-bottom: 2px;
  }

  &__icon {
    width: 20px;
    height: 20px;
  }
}
</style>
