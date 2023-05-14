<template>
    <div class="footer-list">
      <div class="footer-list__line"></div>

        <div v-for="{icon,  label, href} in items" :key="label" class="footer-list__item">
            <a :href="href" class="footer-list__link">
                <img :src="icon" :alt="label" class="footer-list__icon" />
                <span class="footer-list__label">{{label}}</span>
            </a>

        </div>
    </div>
</template>

<script setup>
defineProps({
    items: {type: Array, default: () => []},
})
</script>

<style lang="scss" scoped>
.footer-list {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 40px;

  &__line {
    border-left: 1px solid var(--color-very-light-grey);
    height: 18px;
  }

  &__link {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  &__icon {
    margin-right: 10px;
  }

  &__label {
    color: var(--color-very-light-grey);
    font-size: .75rem;
    line-height: 1rem;
    font-weight: 400;
  }
}
</style>
