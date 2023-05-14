<template>
    <div class="order-form">
        <TSelect/>
        <TInput v-model="email" placeholder="Ваш e-mail"/>
        <TInput v-model="name" placeholder="Ваше имя"/>
        <TRange class="order-form__range" v-model="range"/>
        <TButton icon type="secondary">Прикрепить файл</TButton>
    </div>
    <TButton>Отправить</TButton>
</template>

<script setup>
import TSelect from "@/components/TSelect.vue";
import TInput from "@/components/TInput.vue";
import TRange from "@/components/TRange.vue";
import {ref} from "vue";
import TButton from "@/components/TButton.vue";

const range = ref(75)
const email = ref("")
const name = ref("")
</script>

<style lang="scss" scoped>
.order-form {
    max-width: 1169px;
    width: 100%;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 30px;
    margin-bottom: 35px;

    &__range {
        grid-column: 1 / 3;

        @media screen and (max-width: 768px) {
            grid-column: 1 / 1;
        }
    }

    @media screen and (max-width: 768px) {
        grid-template-columns: repeat(1, 1fr);
    }
}
</style>
