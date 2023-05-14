<template>
    <div class="list">
      <p class="list__header">{{listHeader}}</p>
        <ul class="list__items">
            <li v-for="(item, index) in listItems" :key="index" class="list__lists">{{item}}</li>
        </ul>
    </div>
</template>

<script setup>
defineProps({
    listHeader: {type: String, default: 'At vero eos et accusamus et iusto odio dignissimos ducimus!'},
    listItems: {type: Array, default: ['Totam rem aperiam eaque ipsa', 'Sit voluptatem accusantium doloremque laudantium', 'Sed ut perspiciatis, unde omnis iste natus error']}
})
</script>

<style lang="scss" scoped>
.list {
  &__header {
    font-size: 1.25rem;
    line-height: 1.5rem;
    font-weight: 700;
    margin-bottom: 10px;
  }

  &__lists {
    font-size: 1.25rem;
    line-height: 1.5rem;
    font-weight: 400;
    margin-bottom: 5px;
    position: relative;
    padding-left: 25px;

    &::before {
      content: '-';
      position: absolute;
      top: 0;
      left: 10px;
      z-index: 1;
    }
  }
}
</style>
