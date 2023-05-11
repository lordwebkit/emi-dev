<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'

let linkActive = ref('Home')
let links = ref([
  {
    text: 'Home',
    to: '/'
  },
  {
    text: 'Recipes',
    to: '/recipes'
  },
  {
    text: 'Article',
    to: '/article'
  },
  {
    text: 'Contact',
    to: '/contact'
  },
  {
    text: 'Purchase',
    to: '/purchase'
  }
])

function changePage(text) {
  linkActive.value = text
  document.title = text
}
</script>

<template>
  <header class="header header-row">
    <span class="header__logo">fashion</span>
    <nav class="header__nav">
      <router-link
        v-for="link in links"
        :key="link"
        :to="link.to"
        class="header__link"
        :class="{ 'header__link--active': linkActive === link.text }"
        @click="changePage(link.text)"
      >
        {{ link.text }}
      </router-link>
    </nav>
  </header>
  <RouterView />
</template>

<style lang="scss">
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 80px 19px 80px;

  &__logo {
    font-family: 'PT Serif';
    font-style: normal;
    font-weight: 700;
    font-size: 25px;
    line-height: 33px;
    letter-spacing: 2.5px;
    text-transform: uppercase;
    color: #171717;
    position: relative;
    z-index: 10;

    &::after {
      content: '';
      position: absolute;
      display: inline-block;
      width: 125px;
      height: 6px;
      background-color: var(--gold-color);
      opacity: 0.35;
      bottom: 6px;
      left: 0;
    }
  }

  &__nav {
    width: 368px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__link {
    font-family: 'PT Serif';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 19px;
    color: var(--black-color);

    &--active {
      color: var(--gold-color);
    }
  }
}
</style>
