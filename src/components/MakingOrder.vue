<template>
    <main class="order">
        <div class="order-header">
            <h4 class="order-header__title">Оформление <span class="order-header__title--blue">Заказа</span></h4>
            <p class="order-header__description">Перед заполнением формы ознакомьтесь с нашей схемой работы!</p>
        </div>

        <IconsList class="order__icons" />

        <OrderForm/>
    </main>
</template>

<script setup>
import IconsList from "@/components/IconsList.vue";
import OrderForm from "@/components/OrderForm.vue";
</script>

<style lang="scss" scoped>
.order {
    width: 100%;
    height: 900px;
    background-image: url(@/assets/img/order.svg);
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    background-color: var(--color-light-black);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;

    @media screen and (max-width: 1190px) {
        padding: 150px 20px;
        height: auto;
    }

    &-header {
        margin-bottom: 80px;

        &__title {
            color: var(--color-white);
            font-size: 2.25rem;
            line-height: 2.6875rem;
            font-weight: 800;
            text-align: center;
            margin-bottom: 30px;

            &--blue {
                color: var(--color-primary);
            }
        }

        &__description {
            font-size: 1.125rem;
            line-height: 1.375rem;
            font-weight: 400;
            color: var(--color-light-grey);
        }
    }

    &__icons {
        margin-bottom: 80px;
    }
}
</style>
