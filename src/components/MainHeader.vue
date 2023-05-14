<template>
    <header class="header">
        <div class="header-container">
            <img src="@/assets/img/logo.svg" alt="Logo" class="header-logo">

            <nav class="main-nav">
                <ul class="main-nav__list">
                    <li class="main-nav__item">
                        <a href="#" class="main-nav__link">Бизнес</a>
                    </li>
                    <li class="main-nav__item">
                        <a href="#" class="main-nav__link">О нас</a>
                    </li>
                    <li class="main-nav__item">
                        <a href="#" class="main-nav__link">Цены</a>
                    </li>
                    <li class="main-nav__item">
                        <a href="#" class="main-nav__link">Оформить заказ</a>
                    </li>
                </ul>
            </nav>
        </div>
    </header>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.header {
    height: 100px;
    background-color: var(--color-light-black);
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 100;
    opacity: .9;

  &-container {
    max-width: 1169px;
    height: 100%;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;

      @media screen and (max-width: 1190px) {
          padding: 0 10px;
      }

      @media screen and (max-width: 768px) {
          flex-direction: column;
          padding: 20px 0;
      }
  }

  &-logo {
    cursor: pointer;
  }
}

.main-nav {
  &__list {
    display: flex;
    gap: 60px;

      @media screen and (max-width: 480px) {
          gap: 40px;
      }
  }

  &__link {
    color: var(--color-white);
    font-size: .8125rem;
    line-height: .975rem;
    font-weight: 600;
    text-transform: uppercase;

    &:hover {
      color: var(--color-blue);
    }
  }
}
</style>
