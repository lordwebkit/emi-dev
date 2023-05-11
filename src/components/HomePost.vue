<script setup>
const props = defineProps(['picture', 'name', 'desc', 'date'])
</script>

<template>
  <div class="post">
    <img class="post__picture" :src="props.picture" alt="picture post" />
    <h3 class="post__name">{{ props.name }}</h3>
    <div class="post__info">
      <p class="post__date">{{ props.date.split(' ')[0] }}</p>
      <p class="post__desc">
        <span class="post__desc--gray">By</span>
        {{ props.desc.length > 40 ? `${props.desc.substring(0, 40)} ...` : props.desc }}
      </p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.post {
  width: 370px;
  height: 411px;
  box-shadow: 0px 2px 6px rgba(0, 0, 0, 0.1);
  &:hover {
    cursor: pointer;
  }

  &__picture {
    height: 280px;
    width: 100%;
  }

  &__name {
    font-size: 20px;
    line-height: 28px;
    text-align: center;
    margin-top: 35px;
  }

  &__info {
    display: flex;
    font-size: 12px;
    line-height: 16px;
    color: #666;
    margin-top: 10px;
    justify-content: center;
  }

  &__date {
    margin-right: 5px;
  }

  &__desc--gray {
    color: var(--gray-light-color);
  }
}
</style>
