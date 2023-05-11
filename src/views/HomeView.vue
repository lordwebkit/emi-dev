<script setup>
import HomePosts from '../components/HomePosts.vue'
import HomeAside from '../components/HomeAside.vue'
</script>

<template>
  <div class="home">
    <main class="home__main main-post">
      <div class="main-post__inner container">
        <p class="main-post__vehicle">Vehicle</p>
        <h1 class="main-post__title">One of Saturn’s largest rings may be newer than anyone</h1>
        <div class="main-post__info">
          <p class="main-post__date">June 6, 2019</p>
          <p class="main-post__author">
            <span class="main-post__author--gray">By</span> Rickie Baroch
          </p>
          <p class="main-post__coments">4 comments</p>
        </div>
      </div>
    </main>
    <div class="home__content container">
      <HomePosts />
      <HomeAside />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.home {
  padding-bottom: 100px;
  &__content {
    display: flex;
    justify-content: space-between;
  }
}
.main-post {
  width: 100%;
  height: 700px;
  background: #000 url('@/assets/img/main.jpg') no-repeat center center;

  &__inner {
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-end;
    color: #fff;
    padding-bottom: 59px;
  }

  &__vehicle {
    font-size: 14px;
    line-height: 18px;
    text-transform: uppercase;
  }

  &__title {
    font-weight: 700;
    font-size: 40px;
    line-height: 50px;
    max-width: 560px;
  }

  &__info {
    display: flex;
    justify-content: space-between;
    font-size: 14px;
    line-height: 19px;
    width: 283px;
  }

  &__author--gray {
    color: var(--gray-color);
  }
}
</style>
