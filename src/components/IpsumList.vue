<template>
  <ul>
    <IpsumItem v-for="item in ipsums"
      :key="item.title"
      :item="item"
    />
  </ul>
</template>

<script>
import IpsumItem from './IpsumItem.vue';
export default {
  props: {
    ipsums: Array,
  },
  components: {
    IpsumItem
  }
};
</script>

<style>

</style>
