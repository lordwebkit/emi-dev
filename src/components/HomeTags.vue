<script setup>
import { ref } from 'vue'
const tags = ref([
  'Business',
  'Freelance',
  'Money',
  'Experience',
  'Lifestyle',
  'SEO',
  'Wordpress',
  'Marketing',
  'UX',
  'Modern',
  'Success',
  'Nature'
])
</script>
<template>
  <ul class="tags">
    <li class="tags__tag" v-for="tag in tags" :key="tag">{{ tag }}</li>
  </ul>
</template>
<style lang="scss" scoped>
.tags {
  display: flex;
  flex-wrap: wrap;

  &__tag {
    padding: 6px 15px;
    font-weight: 400;
    font-size: 14px;
    line-height: 19px;
    color: #666666;
    background-color: #f8f9fa;
    margin-right: 7px;
    margin-bottom: 7px;
  }
}
</style>
