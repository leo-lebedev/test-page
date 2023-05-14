<template>
    <footer class="main-footer">
      <p class="main-footer__rights">© 2018 «LoremIpsum.net» Все права защищены.</p>

        <FooterList :items="items1"/>
        <FooterList :items="items2"/>
    </footer>
</template>

<script setup>
import FooterList from "@/components/FooterList.vue";
import {reactive} from "vue";

const items1 = reactive([
    {
        icon: new URL('/src/assets/img/qiwi.svg', import.meta.url),
        label: 'Qiwi wallet',
        href: 'tel: +74951234567'
    },
    {
        icon: new URL('/src/assets/img/y-money.svg', import.meta.url),
        label: 'QYandex Money',
        href: 'tel: +74951234567'
    },
    {
        icon: new URL('/src/assets/img/w-money.svg', import.meta.url),
        label: 'Web Money',
        href: 'tel: +74951234567'
    }
])

const items2 = reactive([
    {
        icon: new URL('/src/assets/img/mail.svg', import.meta.url),
        label: 'info@ipsum228.com',
        href: 'mailto: info@ipsum228.com'
    },
    {
        icon: new URL('/src/assets/img/vk.svg', import.meta.url),
        label: 'Мы вконтакте',
        href: 'tel: +74951234567'
    },
])
</script>

<style lang="scss" scoped>
.main-footer {
  min-height: 80px;
  background-color: var( --color-black--very-light);
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 40px;

  @media (max-width: 1175px) {
    flex-wrap: wrap;
    gap: 20px;
    height: auto;
    padding: 30px 20px;
  }

  &__rights {
    font-size: .75rem;
    line-height: 1rem;
    font-weight: 400;
    color: var(--color-white);
  }
}
</style>
