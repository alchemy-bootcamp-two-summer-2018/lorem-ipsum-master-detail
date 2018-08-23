<template>
    <div>
        <IpsumList :ipsums="ipsums"
          :selected="selectedIpsum"
          :onSelect="handleSelect"
        />
        <Ipsum
            :ipsum="selectedIpsum"
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
    }
  }
};
</script>

<style>

</style>
