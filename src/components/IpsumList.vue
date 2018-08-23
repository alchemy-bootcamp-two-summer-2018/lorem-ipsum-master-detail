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

<style>

ul {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    grid-gap: 20px;
    align-items: center;
    justify-content: center;
    max-width: 1200px;
    margin-left:80px

   
}

</style>
