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

<style scoped>

ul { 
  display: grid; 
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); 
  grid-gap: 5px; 
}

</style>
