<template>
  <ul>
    <IpsumItem v-for="ipsum in ipsums"
      :key="ipsum.key"
      :ipsum="ipsum"
      :selected="selected"
      :onSelect="onSelect"
    />
  </ul>
</template>

<script>
import IpsumItem from './IpsumItem.vue';
export default {
  props: {
    ipsums: Array,
    selected: Object,
    onSelect: Function
  },
  components: {
    IpsumItem
  }
};
</script>

<style scoped>

ul { 
  display: grid; 
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); 
  grid-gap: 5px; 
}

</style>
