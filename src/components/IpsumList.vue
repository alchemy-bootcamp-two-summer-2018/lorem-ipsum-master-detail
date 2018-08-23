<template>

<ul>
    <IpsumItem v-for="ipsum in ipsums"
    :key="ipsum.title"
    :ipsum="ipsum"
    :selected="selected"
    :onSelect="onSelect"/>

</ul>

</template>

<script>
//displays title & category of all ipsums in display

import IpsumItem from './IpsumItem.vue';

export default {

  props: {
    ipsums: Array,
    selected: Object,
    onSelect: Function
  },

  components: {
    IpsumItem,
  }

};
</script>

<style scoped>



ul {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    justify-content: center;
    align-content: center;
    margin: 0;
    grid-gap: 20px;
    padding: 30px 60px 30px 60px;
}

</style>
