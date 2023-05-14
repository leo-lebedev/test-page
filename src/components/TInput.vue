<template>
    <div class="t-input">
        <input type="text" class="t-input__input" :value="modelValue" @input="$emit('update:model-value', $event.target.value)" :placeholder="placeholder" />
    </div>
</template>

<script setup>
defineProps({
    placeholder: {
        type: String,
        default: ''
    },
    modelValue: {
        type: String,
        default: ''
    }
})
</script>

<style lang="scss" scoped>
.t-input {
    width: 100%;

  &__input {
    border-radius: 3px;
    border: 1px solid var(--color-white);
    height: 38px;
    width: 100%;
    padding: 12px 10px;
    background-color: var(--color-white);
    font-size: 1.125rem;
    line-height: 1.375rem;
    font-weight: 400;
    color: var(--color-black-light);
  }
}
</style>
