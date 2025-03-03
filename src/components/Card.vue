<template>
  <div
    :class="[
      'card',
      size && `card-${size}`,
      align && `card-${align}`,
      type && `card-${type}`,
      hoverable && 'card-hoverable',
    ]"
  >
    <slot></slot>
  </div>
</template>

<script lang="ts">
import { BreakpointsLabel } from "../utils/breakpoins";
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    size: {
      type: String,
      required: true,
      default: "s",
      validator: (value: string): boolean => {
        return BreakpointsLabel.includes(value);
      },
    },
    align: {
      type: String,
      required: false,
      default: "center",
    },
    type: {
      type: String,
      required: false,
      default: "shadow",
    },
    hoverable: {
      type: Boolean,
      required: false,
      default: false,
    },
  },
});
</script>

<style lang="scss" scoped>
@import "../assets/styles/color";

.card {
  display: flex;
  flex-direction: column;
  padding: 10px;
  border-radius: 0.5rem;
  width: 100%;

  &-shadow {
    transition: box-shadow 0.3s cubic-bezier(0.25, 0.1, 0.25, 0.1);
    box-shadow: 0 2px 8px rgba(18, 17, 36, 0.04),
      0 4px 32px rgba(18, 17, 36, 0.08);
  }

  &-hoverable:hover {
    box-shadow: 0 2px 8px rgba(18, 17, 36, 0.1),
      0 4px 32px rgba(18, 17, 36, 0.2);
  }

  &-border {
    border: 1px solid $color-lightgray;
  }

  &-xs {
    max-width: calc(300px - 3rem);
  }

  &-sm {
    max-width: calc(500px - 3rem);
  }

  &-md {
    max-width: calc(960px - 3rem);
  }

  &-lg {
    max-width: calc(1280px - 3rem);
  }

  &-xl {
    max-width: calc(1920px - 3rem);
  }

  &-left {
    margin-right: auto;
  }

  &-center {
    margin-left: auto;
    margin-right: auto;
  }

  &-right {
    margin-left: auto;
  }
}
</style>
