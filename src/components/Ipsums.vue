<template>
  <div>
    <AddIpsum/>
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
  }
};
</script>