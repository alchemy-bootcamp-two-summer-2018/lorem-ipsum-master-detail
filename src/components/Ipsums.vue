<template>
    <div>
        <IpsumList :ipsums="ipsums"
          :selected="selectedIpsum"
          :onSelect="handleSelect"
        />
    </div>
</template>

<script>
import ipsums from '../services/ipsumsApi.js';
import IpsumList from './IpsumList.vue';
export default {
  data: function() {
    return {
      ipsums: ipsums,
      selectedIpsum: null
    };
  },
  components: {
    IpsumList
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
