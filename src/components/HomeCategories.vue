<script setup>
import { ref } from 'vue'
const categories = ref([
  { name: 'Fashion', quantity: 23 },
  { name: 'Style & clothes', quantity: 7 },
  { name: 'Minimalism', quantity: 16 },
  { name: 'Black & White', quantity: 5 },
  { name: 'Modern clothes', quantity: 12 }
])
</script>
<template>
  <ul class="categories">
    <li class="categories__item" v-for="category in categories" :key="category">
      <p class="categories__name">{{ category.name }}</p>
      <p class="categories__quantity">({{ category.quantity }})</p>
    </li>
  </ul>
</template>

<style lang="scss" scoped>
.categories {
  width: 100%;

  &__item {
    display: flex;
    justify-content: space-between;
    padding: 15px 0;
    border-bottom: 1px solid #e5e5e5;
    font-size: 14px;
    line-height: 19px;
    color: #666666;

    &:nth-last-child(1) {
      border-bottom: none;
    }
  }
}
</style>
