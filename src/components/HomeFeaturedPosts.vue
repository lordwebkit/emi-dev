<script setup>
import { ref } from 'vue'
import HomeFeaturedPost from './HomeFeaturedPost.vue'

const posts = ref([
  {
    id: 1,
    theme: 'jeans',
    name: 'One of Saturn’s largest rings may be newer than anyone',
    date: 'June 6, 2019',
    author: 'Rickie Baroch'
  },
  {
    id: 2,
    theme: 'jeans',
    name: 'One of Saturn’s largest rings may be newer than anyone',
    date: 'June 6, 2019',
    author: 'Rickie Baroch'
  },
  {
    id: 3,
    theme: 'jeans',
    name: 'One of Saturn’s largest rings may be newer than anyone',
    date: 'June 6, 2019',
    author: 'Rickie Baroch'
  }
])
</script>
<template>
  <div class="featured-posts">
    <HomeFeaturedPost
      v-for="post in posts"
      :key="post"
      :id="post.id"
      :theme="post.theme"
      :name="post.name"
      :date="post.date"
      :author="post.author"
    />
  </div>
</template>

<style lang="scss" scoped></style>
