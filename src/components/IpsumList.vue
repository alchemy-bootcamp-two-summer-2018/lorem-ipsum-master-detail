<template>
  <ul>
    <IpsumItem v-for="ipsum in ipsums"
      :key="ipsum.title"
      :name="ipsum.title"
      :category="ipsum.category"
      :select="onSelect"/>
  </ul>
</template>

<script>
import IpsumItem from './IpsumItem.vue';

export default {
  props: {
    onSelect: Function,
    ipsums: Object
  },
  components: {
    IpsumItem
  }

};
</script>

<style scoped>


</style>
