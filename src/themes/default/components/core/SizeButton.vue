<template>
  <button
    class="
      p0 bg-white brdr-1 brdr-c-lightgray-secondary
      brdr-square h5 c-lightgray-secondary size-button
    "
    :class="{ active: active }"
    @click="switchFilter(id, label)"
    :aria-label="$t('Select size ') + label"
  >
    {{ label }}
  </button>
</template>

<script>
import { coreComponent } from 'lib/themes'

export default {
  mixins: [coreComponent('core/SizeButton')]
}
</script>

<style lang="scss" scoped>
  @import '~theme/css/base/global_vars';
  $gray-secondary: map-get($colors, gray-secondary);
  $alto: map-get($colors, alto);

  .size-button {
    width: 40px;
    height: 40px;

    &:hover,
    &:focus {
      border-width: 2px;
    }

    &.active {
      border-color: $gray-secondary;
      border-width: 2px;
      color: $gray-secondary;
    }

    &:disabled {
      border-color: $alto;
      color: $alto;
      cursor: not-allowed;

      &:hover,
      &:after {
        border-width: 1px;
      }
    }
  }
</style>
