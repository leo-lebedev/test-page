<template>
  <button :class="computedClasses" class="button">
      <img class="button__icon" src="@/assets/img/file.svg" v-if="icon" alt="Icon">
    <slot />
  </button>
</template>

<script setup>
import { computed } from "vue";

const props = defineProps({
    type: { type: String, default: "primary", validator: v => ["primary", "secondary", "outline"].includes(v) },
    size: { type: String, default: "small", validator: v => ["small", "large"].includes(v) },
    icon: { type: Boolean, default: false },
});

const computedClasses = computed(() => {
  return [{
      "button--primary": props.type === "primary",
      "button--outline": props.type === "outline",
      "button--secondary": props.type === "secondary",
      "button--small": props.size === "small",
      "button--large": props.size === "large"

  }];
});
</script>

<style lang="scss" scoped>
.button {
  min-width: 183px;
  height: 43px;
  border-radius: 4px;
  font-size: .8125rem;
  line-height: 1rem;
  font-weight: 400;
  text-transform: uppercase;
  display: flex;
  align-items: center;
  justify-content: center;

  &:hover {
    opacity: .9;
  }

  &--primary {
    background-color: var(--color-primary);
    border: 1px solid var(--color-white);
    color: var(--color-white);
  }

  &--outline {
    background-color: var(--color-white);
    border: 1px solid var(--color-grey);
    color: var(--color-black);
  }

  &--secondary {
    background-color: var(--color-white);
    border: 2px solid var(--color-primary);
    color: var(--color-black);
  }

  &--large {
    width: 310px;
  }

  &__icon {
    margin-right: 10px;
  }

  @media screen and (max-width: 480px) {
    min-width: 140px;
  }
}
</style>
