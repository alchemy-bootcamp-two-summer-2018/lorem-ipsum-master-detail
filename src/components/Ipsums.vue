<template>
  <div>
    <AddIpsum
      :onUpdate="handleUpdate"/>
    <IpsumList
      :ipsums="ipsums"/>
  </div>
</template>

<script>
import IpsumList from './IpsumList.vue';
import data from '../services/data.js';
import AddIpsum from './AddIpsum.vue';

export default {
  data() {
    return {
      ipsums: data.getData()
    };
  },
  components: {
    IpsumList,
    AddIpsum
  },
  methods: {
    handleUpdate(updated) {
      const index = this.ipsums.findIndex(ipsum => {
        return ipsum.title === updated.title;
      });

      if(index !== -1) {
        this.ipsums.splice(index, 1, updated);
      }
    }
  }
};
</script>