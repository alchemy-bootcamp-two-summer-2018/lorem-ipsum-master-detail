<template>
  <main>
    <AddIpsum 
      :onAdd="handleAdd"
    />
    <IpsumList 
      :onSelect="handleSelect"
      :ipsums="ipsumDB"
    />
    <Ipsum 
      :onUpdate="handleUpdate"
      :ipsum="selected"
    />
  </main>
</template>

<script>
import AddIpsum from './AddIpsum.vue';
import IpsumList from './IpsumList.vue';
import Ipsum from './Ipsum.vue';

import ipsumDB from '../services/ipsumDB.js';

export default {
  props: {
    
  },
  components: {
    AddIpsum, IpsumList, Ipsum
  },
  data() {
    return {
      ipsumDB,
      selected: null,
    };
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
