<template>
  <div>
    <IpsumList
      :ipsums="ipsums"/>
  </div>
</template>

<script>
import IpsumList from './components/IpsumList.vue';
import data from './services/data.js';

export default {
  data() {
    return {
      ipsums: data.getData()
    };
  },
  components: {
    IpsumList
  }
};
</script>