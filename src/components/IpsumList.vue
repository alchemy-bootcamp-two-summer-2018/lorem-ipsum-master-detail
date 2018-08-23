<template>
  <ul>
    <IpsumItem 
      v-for="ipsum in ipsums"
      :key="ipsum.title"
      :category="ipsum.category"
      :ipsum="ipsum"
      :onSelect="onSelect"
      :selected="selected"
    />
  </ul>
</template>

<script>
import IpsumItem from './IpsumItem.vue';

export default {
  props: {
    onSelect: Function,
    ipsums: Array,
    selected: Object
  },
  components: {
    IpsumItem
  },
};
</script>

<style scoped>

ul {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  grid-gap: 10px;
  margin: 20px;
  
}


</style>
