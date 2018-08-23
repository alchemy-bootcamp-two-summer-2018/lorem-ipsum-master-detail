<template>
  <div>
    <AddIpsum
      :onAdd="handleAdd"/>
    <Ipsum
      :ipsumItem="selectedIpsum"
      :onUpdate="handleUpdate"
    />
    <IpsumList
      :ipsums="ipsums"
      :onSelect="handleSelect"
      :selected="selectedIpsum"
    />
  </div>
</template>

<script>
import IpsumList from './IpsumList.vue';
import data from '../services/data.js';
import AddIpsum from './AddIpsum.vue';
import Ipsum from './Ipsum.vue';

export default {
  data() {
    return {
      ipsums: data.getData(),
      selectedIpsum: null
    };
  },
  components: {
    IpsumList,
    AddIpsum,
    Ipsum
  },
  methods: {
    handleAdd(ipsum) {
      this.ipsums.push(ipsum);
    },
    handleSelect(ipsumItem) {
      this.selectedIpsum = ipsumItem;
    },
    handleUpdate(updated) {
      const index = this.ipsums.findIndex(ipsumItem => {
        return ipsumItem.key === updated.key;
      });

      if(index !== -1) {
        this.ipsums.splice(index, 1, updated);
        this.selectedIpsum = updated;
      }
    }
  }
};
</script>