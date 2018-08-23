<template>
  <main>
    <AddIpsum 
      :onAdd="handleAdd"
    />
    <IpsumList 
      :onSelect="handleSelect"
      :ipsums="ipsumDB"
      :selected="selected"
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
    handleAdd(ipsum) {
      this.ipsumDB.push(ipsum);
    },
    handleUpdate(updated) {
      const index = this.ipsumDB.findIndex(ipsum => {
        return ipsum.key === updated.key;
      });

      if(index !== -1) {
        this.ipsumDB.splice(index, 1, updated);
        this.selected = updated;
      }
    },
    handleSelect(ipsum) {
      this.selected = ipsum;
    },
  },
};

</script>

<style scoped>


</style>
