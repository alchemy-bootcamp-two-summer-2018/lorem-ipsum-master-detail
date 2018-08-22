<template>
    <div>
        <IpsumItem v-for="ipsum in ipsums"
            :key="ipsum.title"
            :ipsum="ipsum"/>
    </div>
</template>

<script>
import IpsumItem from './components/IpsumItem.vue';

export default {
  props: {
    ipsums: Array
  },
  components: {
    IpsumItem
  }
};

</script>

<style>

</style>
