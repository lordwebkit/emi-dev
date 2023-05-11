<script setup>
import HomeAboutAuthor from './HomeAboutAuthor.vue'
import HomeFeaturedPosts from './HomeFeaturedPosts.vue';
import HBtn from './HBtn.vue'
</script>
<template>
  <div class="aside">
    <HBtn class="aside__about-author">About the author</HBtn>
    <HomeAboutAuthor />
    <HBtn class="aside__featured-posts">Featured posts</HBtn>
    <HomeFeaturedPosts />
  </div>
</template>
<style lang="scss" scoped>
.aside {
  padding-top: 60px;
  width: 270px;

  &__about-author {
    margin-bottom: 20px;
  }

  &__featured-posts {
    margin-top: 70px;
  }
}
</style>
