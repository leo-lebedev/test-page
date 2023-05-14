<template>
    <div class="icon-list-container">
        <div v-for="{icon, title} in listData" :key="title" class="icon-list">
            <img :src="icon" :alt="title" class="icon-list__img" />
            <p class="icon-list__title">{{title}}</p>
        </div>
    </div>
</template>

<script setup>
import {reactive} from "vue";

const listData = reactive([
    {
        icon: new URL('/src/assets/img/icon1.svg', import.meta.url),
        title: 'Lorem ipsum dolor sit amet',
    },
    {
        icon: new URL('/src/assets/img/icon2.svg', import.meta.url),
        title: 'Сonsecteturadipiscing elit',
    },
    {
        icon: new URL('/src/assets/img/icon2.svg', import.meta.url),
        title: 'Sed do eiusmod tempor',
    },
    {
        icon: new URL('/src/assets/img/icon3.svg', import.meta.url),
        title: 'Esse cillum doloreeu fugiat',
    },
    {
        icon: new URL('/src/assets/img/icon5.svg', import.meta.url),
        title: 'Excepteur sint occaecat cupidatat non proident',
    },
])
</script>

<style lang="scss" scoped>
.icon-list {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;

    &:not(:last-child):before {
        content: '. . . . .';
        position: absolute;
        top: 15px;
        right: -70px;
        color: var(--color-dark-grey);
        font-size: 2.5rem;
    }

    &-container {
        display: flex;
        gap: 51px;


        @media (max-width: 996px) {
            display: grid;
            grid-template-columns: repeat(3, minmax(200px, 1fr));
            gap: 25px;
        }

        @media (max-width: 680px) {
            grid-template-columns: repeat(2, minmax(100px, 1fr));
        }
    }

    &__img {
        width: 100px;
        height: 100px;
        margin-bottom: 20px;
    }

    &__title {
        font-size: 1rem;
        line-height: 1.1875rem;
        font-weight: 400;
        color: var(--color-white);
        max-width: 195px;
        text-align: center;
    }

    @media (max-width: 996px) {
        &:before {
            display: none;
        }
    }
}
</style>
