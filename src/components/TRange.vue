<template>
    <div class="t-range">
        <div class="t-range__header">
            <p>Sed ut perspiciatis, unde omnis iste natus</p>
            <p>{{modelValue}} %</p>
        </div>
        <input type="range" class="t-range__input" min="0" max="100" :value="modelValue" @input="$emit('update:model-value', $event.target.value)">
    </div>
</template>

<script setup>
defineProps({
    modelValue: {
        type: Number,
        default: 0
    }
})
</script>

<style lang="scss" scoped>
.t-range {
  &__header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 1.125rem;
    line-height: 1.375rem;
    font-weight: 400;
    color: var(--color-white);
    margin-bottom: 5px;
  }

    &__input {
        -webkit-appearance: none;
        -moz-appearance: none;
        appearance: none;
        height: 10px;
        width: 100%;
        background-color: var(--color-light-grey);
        border: 1px solid var(--color-white);
        border-radius: 6px;

        &::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            width: 20px;
            height: 20px;
            background-color: var(--color-blue-dark);
            border: 3px solid var(--color-very-blue-dark);
            border-radius: 50%;
        }
        &::-moz-range-thumb {
            width: 20px;
            height: 20px;
            background-color: var(--color-blue-dark);
            border: 3px solid var(--color-very-blue-dark);
            border-radius: 50%;
        }
        &::-ms-thumb {
            width: 20px;
            height: 20px;
            background-color: var(--color-blue-dark);
            border: 3px solid var(--color-very-blue-dark);
            border-radius: 50%;
        }
    }
}
</style>
