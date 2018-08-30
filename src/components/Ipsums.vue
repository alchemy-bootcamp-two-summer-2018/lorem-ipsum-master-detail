<template>
    <div>
      <IpsumList :ipsums="ipsums"
        :selected="selectedIpsum"
        :onSelect="handleSelect"
      />
      <Ipsum
          :ipsum="selectedIpsum"
          :onUpdate="handleUpdate"
          :onAdd="handleAdd"
      />
      <AddIpsum 
        :onAdd="handleAdd"
      />
    </div>
</template>

<script>
import ipsums from '../services/ipsumsApi.js';
import IpsumList from './IpsumList.vue';
import Ipsum from './Ipsum.vue';
import AddIpsum from './AddIpsum.vue';

export default {
  data: function() {
    return {
      ipsums: ipsums,
      selectedIpsum: null
    };
  },
  components: {
    IpsumList,
    Ipsum,
    AddIpsum
  },
  methods: {
    handleSelect(ipsum) {
      this.selectedIpsum = ipsum;
    },
    handleUpdate(updated) {
      const index = this.ipsums.findIndex(ipsum => {
        return ipsum.title === updated.title;
      });

      //It's comparing new title to the previous title. 
      //Need to switch what's being identified to an ID.
      console.log(updated)
      console.log(index)
      if(index !== -1) {
        this.ipsums.splice(index, 1, updated);
        this.selectedIpsum = updated;
      }
    },
    handleAdd(added) {
      return this.ipsums.push(added)
    },
  }
};
</script>

<style>

</style>
