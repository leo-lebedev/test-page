<template>
    <div class="t-select" :class="{ 't-select--open': isOpen }">
        <div class="t-select__option" @click="toggle">
            <p class="t-select__label">{{ selectedOption.label || selectedOption }}</p>
            <img src="@/assets/img/arrow.svg" alt="Arrow" class="t-select__arrow" :class="{ 't-select__arrow-up': isOpen, 't-select__arrow-down': !isOpen }">
        </div>
        <div class="t-select-options" v-show="isOpen">
            <div v-for="(option, index) in options" :key="index" class="t-select-options__option" @click="select(option)">
                {{ option.label }}
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const options = [
    { value: 'option-1', label: 'Option 1' },
    { value: 'option-2', label: 'Option 2' },
    { value: 'option-3', label: 'Option 3' },
    { value: 'option-4', label: 'Option 4' },
    { value: 'option-5', label: 'Option 5' },
    { value: 'option-6', label: 'Option 6' },
    { value: 'option-7', label: 'Option 7' },
    { value: 'option-8', label: 'Option 8' },
    { value: 'option-9', label: 'Option 9' },
    { value: 'option-10', label: 'Option 10' },
    { value: 'option-11', label: 'Option 11' },
]

const isOpen = ref(false)
const selectedOption = ref('Выберите тип системы')

function toggle() {
    isOpen.value = !isOpen.value
}

function select(option) {
    selectedOption.value = option
    isOpen.value = false
}

function handleClickOutside(event) {
    if (!event.target.closest('.t-select')) {
        isOpen.value = false
    }
}

onMounted(() => {
    window.addEventListener('click', handleClickOutside)
})

onUnmounted(() => {
    window.removeEventListener('click', handleClickOutside)
})
</script>

<style scoped lang="scss">
.t-select {
    position: relative;
    width: 100%;
    height: 38px;
    border: 1px solid var(--color-white);
    background-color: var(--color-white);
    color: var(--color-black-light);
    border-radius: 3px;
    padding: 7px 10px;
    cursor: pointer;

    &__option {
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    &__label {
        font-size: 1.125rem;
        line-height: 1.375rem;
        font-weight: 400;
    }

    &__arrow-up {
        transform: rotate(180deg);
    }

    &--open {
        background-color: var(--color-black--very-light);

        .t-select__label {
            color: var(--color-white);
        }
    }

    &-options {
        position: absolute;
        top: 100%;
        left: 0;
        width: 100%;
        max-height: 180px;
        overflow-y: auto;
        border: 1px solid var(--color-black--very-light);
        background-color: var(--color-black-light);
        z-index: 1;

        &__option {
            padding: 7px 10px;
            cursor: pointer;
            color: var(--color-white);

            &:hover {
                background-color: var(--color-black--very-light);
                color: var(--color-vary-blue);
            }
        }
    }

    @media screen and (max-width: 955px) {
        padding: 10px;
    }

    @media screen and (max-width: 450px) {
        padding: 12px 10px;
    }
}
</style>
