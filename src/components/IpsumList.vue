<template>
    <div>
        <IpsumItem v-for="ipsum in ipsums"
            :key="ipsum.title"
            :ipsum="ipsum"
            :selected="selected"
            :onSelect="onSelect"/>
    </div>
</template>

<script>
import IpsumItem from './IpsumItem.vue';

export default {
  props: {
    ipsums: Array,
    onSelect: Function,
    selected: Object
  },
  components: {
    IpsumItem
  }
};

</script>

<style>

</style>
