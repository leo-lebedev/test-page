<template>
    <div class="hero">
        <div class="hero-container">
            <h1 class="hero__header"><span class="hero__header--blue">Lorem ipsum</span> dolor sit <br> amet consectetur <span class="hero__header--blue">adipiscing</span></h1>

            <HeroList class="hero__list"/>

            <div class="hero__button">
                <TButton class="hero__button--blue">заказать</TButton>
                <TButton type="outline">подробнее</TButton>
            </div>
        </div>
    </div>
</template>

<script setup>

import HeroList from "@/components/HeroList.vue";
import TButton from "@/components/TButton.vue";
</script>

<style lang="scss" scoped>
.hero {
    width: 100%;
    height: 950px;
    background-image: url(@/assets/img/hero.svg);
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;

    @media screen and (max-width: 1190px) {
        display: flex;
        justify-content: center;
        padding: 20px;
    }

    &-container {
        padding-top: 203px;
        margin-left: 19.5%;

        @media screen and (max-width: 1190px) {
            margin-left: 0;
        }
    }

    &__header {
        font-size: 3rem;
        line-height: 3.5812rem;
        font-weight: 800;
        text-transform: uppercase;

        &--blue {
            color: var(--color-primary);
        }
    }

    &__list {
        margin-top: 80px;
    }

    &__button {
        display: flex;
        margin-top: 80px;

        &--blue {
            margin-right: 30px;

            @media screen and (max-width: 450px) {
                margin-right: 15px;
            }
        }
    }
}
</style>
