<script setup>
import { ref, computed, watch } from 'vue'
import { usePostsStore } from '../stores/posts'
import HomePost from './HomePost.vue'

const store = usePostsStore()
store.getPosts()

const currentPostsPage = ref(1)
const postsPerPage = ref(10)

let pages = ref([1, 2, 3])
let reverse = ref(false)

const displayedPosts = computed(() => {
  const start = (currentPostsPage.value - 1) * postsPerPage.value
  const end = start + postsPerPage.value

  return store.posts.slice(start, end)
})

const pageCount = computed(() => {
  const pageCount = Math.ceil(store.posts.length / postsPerPage.value)
  return pageCount > 1 ? pageCount : 1
})

watch(
  currentPostsPage,
  (newValue, oldValue) => {
    if (newValue > 2 && newValue < 4 && newValue > oldValue) {
      pages.value = pages.value.map((page) => page + 1)
    } else if (newValue < oldValue) {
      pages.value = pages.value.map((page) => page - 1)
    }
  },
  { immediate: true }
)
</script>

<template>
  <section class="posts">
    <div class="posts__inner container">
      <div class="posts__post-wrapper">
        <HomePost
          class="posts__post"
          v-for="post in displayedPosts"
          :key="post.ID"
          :picture="post.picture"
          :name="post.name"
          :desc="post.desc"
          :date="post.date_create"
        />
      </div>
      <div class="posts__pages posts-pages">
        <button
          class="posts-pages__button posts-pages__old"
          @click="currentPostsPage > 1 ? currentPostsPage-- : currentPostsPage"
        >
          <i class="posts-pages__arrow"></i>
          older post
        </button>
        <ul
          class="posts-pages__pagination pages-pagination"
          :class="{ 'pages-pagination--reverse': reverse }"
        >
          <li class="pages-pagination__item">
            <a
              class="pages-pagination__link"
              :class="{ 'pages-pagination__link--active': currentPostsPage === 1 }"
              @click.prevent="currentPostsPage = pages[0]"
              >{{ pages[0] }}</a
            >
          </li>
          <li class="pages-pagination__item">
            <a
              class="pages-pagination__link"
              :class="{
                'pages-pagination__link--active':
                  currentPostsPage > 1 && currentPostsPage < pageCount - 1
              }"
              @click.prevent="currentPostsPage = pages[1]"
              >{{ pages[1] }}</a
            >
          </li>
          <li class="pages-pagination__item">
            <a class="pages-pagination__link" @click.prevent="currentPostsPage = pages[2]">{{
              pages[2]
            }}</a>
          </li>
          <li>...</li>
          <li class="pages-pagination__item">
            <a
              class="pages-pagination__link"
              :class="{ 'pages-pagination__link--active': currentPostsPage === pageCount }"
              @click.prevent="currentPostsPage = pageCount"
              >{{ pageCount }}</a
            >
          </li>
        </ul>
        <button
          class="posts-pages__button posts-pages__next"
          @click="currentPostsPage < pageCount ? currentPostsPage++ : currentPostsPage"
        >
          next post
          <i class="posts-pages__arrow posts-pages__arrow--next"></i>
        </button>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.posts {
  &__inner {
    padding-top: 60px;
    display: flex;
    max-width: 770px;
    flex-direction: column;
  }

  &__post-wrapper {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }

  &__post {
    margin-bottom: 30px;
  }
}

.posts-pages {
  width: 509px;
  height: 50px;
  padding: 0 25px;
  border: 1px solid #e5e5e5;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;

  &__button {
    text-transform: uppercase;
    display: flex;
    align-items: center;
    font-family: 'Hanken Grotesk';
    font-size: 14px;
    line-height: 16px;
  }

  &__arrow {
    display: inline-block;
    background-image: url('@/assets/icon/arrow.svg');
    width: 4px;
    height: 8px;
    margin-right: 10px;

    &--next {
      transform: rotate(180deg) translateY(-1px);
      margin-right: 0;
      margin-left: 10px;
    }
  }
}

.pages-pagination {
  display: flex;
  align-items: center;
  width: 50%;
  justify-content: space-between;

  &--reverse {
    flex-direction: row-reverse;
  }

  &__link {
    font-family: 'HK Grotesk';
    font-size: 16px;
    line-height: 16px;
    cursor: pointer;
    color: var(--black-color);

    &--active {
      color: var(--gold-color);
    }
  }
}
</style>
