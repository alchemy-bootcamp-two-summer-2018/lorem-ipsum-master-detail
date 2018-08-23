<template>
    <div>
        <IpsumList :ipsums="ipsums"
          :selected="selectedIpsum"
          :onSelect="handleSelect"
        />
        <Ipsum
            :ipsum="selectedIpsum"
            :onUpdate="handleUpdate"
        />
    </div>
</template>

<script>
import ipsums from '../services/ipsumsApi.js';
import IpsumList from './IpsumList.vue';
import Ipsum from './Ipsum.vue';

export default {
  data: function() {
    return {
      ipsums: ipsums,
      selectedIpsum: null
    };
  },
  components: {
    IpsumList,
    Ipsum
  },
  methods: {
    handleSelect(ipsum) {
      this.selectedIpsum = ipsum;
    },
    handleUpdate(updated) {
      const index = this.ipsums.findIndex(ipsum => {
        return ipsum.title === updated.title;
      });

      if(index !== -1) {
        this.ipsums.splice(index, 1, updated);
        this.selectedIpsum = updated;
      }
    }
  }
};
</script>

<style>

</style>
