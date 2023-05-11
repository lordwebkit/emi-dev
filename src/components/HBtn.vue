<template>
  <button class="h-btn">
    <slot></slot>
  </button>
</template>

<style lang="scss" scoped>
.h-btn {
  padding: 15px 0;
  width: 100%;
  border: 1px solid #e5e5e5;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  font-size: 16px;
  line-height: 21px;
}
</style>
