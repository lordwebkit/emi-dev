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
const socialList = ref(['facebook', 'twitter', 'pinterest', 'google', 'behance', 'instagram'])

function changePage(text) {
  linkActive.value = text
  document.title = text
}
</script>

<template>
  <header class="header header-row">
    <span class="header__logo logo">fashion</span>
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
  <footer class="footer">
    <div class="footer__inner container">
      <span class="footer__logo logo">fashion</span>
      <nav class="footer__nav">
        <router-link
          v-for="link in links"
          :key="link"
          :to="link.to"
          class="footer__link"
          :class="{ 'footer__link--active': linkActive === link.text }"
          @click="changePage(link.text)"
        >
          {{ link.text }}
        </router-link>
      </nav>
      <ul class="footer__social">
        <li class="footer__social-item" v-for="social in socialList" :key="social">
          <img
            class="footer__social-icon"
            :src="`src/assets/icon/social/${social}.svg`"
            alt="social icon"
          />
        </li>
      </ul>
      <span class="footer__br"></span>
      <p class="footer__copyright">@2019 Logwork. All Right Reserved.</p>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 80px 19px 80px;

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

.logo {
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

.footer {
  text-align: center;

  &__nav {
    width: 368px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 0 auto;
    margin-top: 60px;
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

  &__social {
    width: 304px;
    height: 34px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    margin-top: 29px;
    margin-bottom: 40px;
  }

  &__social-item {
    width: 34px;
    height: 34px;
    border: 1px solid #e5e5e5;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  &__br {
    width: 100%;
    height: 1px;
    background-color: #e5e5e5;
    display: inline-block;
  }

  &__copyright {
    text-align: center;
    font-size: 14px;
    line-height: 18px;
    color: #666666;
    margin-top: 30px;
    margin-bottom: 226px;
  }
}
</style>
