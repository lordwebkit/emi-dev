<script setup>
import HomeAboutAuthor from './HomeAboutAuthor.vue'
import HomeFeaturedPosts from './HomeFeaturedPosts.vue'
import HomeCategories from './HomeCategories.vue'
import HBtn from './HBtn.vue'
import HomeSocial from './HomeSocial.vue'
import HomeTags from './HomeTags.vue'
</script>
<template>
  <div class="aside">
    <HBtn class="aside__about-author">About the author</HBtn>
    <HomeAboutAuthor />
    <HBtn class="aside__featured-posts">Featured posts</HBtn>
    <HomeFeaturedPosts />
    <HBtn class="aside__categories">Categories</HBtn>
    <HomeCategories />
    <HBtn class="aside__social">Social media</HBtn>
    <HomeSocial />
    <HBtn class="aside__tags">Tags</HBtn>
    <HomeTags />
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

  &__categories {
    margin-top: 70px;
  }

  &__social {
    margin-top: 70px;
    margin-bottom: 20px;
  }

  &__tags {
    margin-top: 70px;
    margin-bottom: 20px;
  }
}
</style>
