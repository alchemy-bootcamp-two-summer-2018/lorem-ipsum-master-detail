<template>
  <main>
    <AddIpsum 
      :onAdd="handleAdd"
      :onCancel="handleCancel"
      :ipsum="ipsum"
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
    handleAdd() {
      const ipsum = {
        title: this.ipsum.title,
        category: this.ipsum.category
      };
      this.handleUpdate(ipsum);
    },
    handleUpdate(ipsum) {
      this.ipsumDB.push(ipsum);
    },
    handleSelect(ipsum) {
      this.selected = ipsum;
    },
  },
};

</script>

<style scoped>


</style>
