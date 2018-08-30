<template>
    <ul>
        <IpsumItem v-for="ipsum in ipsums"
        :key="ipsum.title"
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
    ipsum: Object,
    ipsums: Array,
    selected: Object,
    onSelect: Function
  },
  components: {
    IpsumItem
    
  }
};
</script>

<style>
ul {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  grid-gap: 10px;
}
</style>
