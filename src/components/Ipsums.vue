<template>
  <main>
    <AddIpsum/>
    <IpsumList/>
    <Ipsum/>
  </main>
</template>

<script>
import AddIpsum from './AddIpsum.vue';
import IpsumList from './IpsumList.vue';
import Ipsum from './Ipsum.vue';

import data from '../services/data.js';

export default {

  components: {
    AddIpsum, IpsumList, Ipsum
  },

  methods: {
    handleAdd () {
      // TODO
    },
    handleUpdate () {
    // TODO
    },
    handleSelect () {
    // TODO
    },
  },
};

</script>

<style scoped>


</style>
