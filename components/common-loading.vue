<script setup lang="ts">
defineProps({
  showInFirst: {
    type: Boolean,
    default: true
  }
});

const isFirstLoad = useFirstLoad();
</script>

<template>
  <div :class="{hide: !showInFirst && isFirstLoad}" class="common-loading flexc">
    <svg-icon name="loading" />
    <span>Loading...</span>
  </div>
</template>

<style lang="scss">
@import "assets/style/var";

.common-loading {
  &.hide {
    display: none;
  }

  > svg {
    @include square(60px);

    fill: $theme-color-darken;
  }

  > span {
    font-size: 14px;
    margin-top: 10px;
  }
}
</style>
