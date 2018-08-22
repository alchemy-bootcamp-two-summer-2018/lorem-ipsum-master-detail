<template>
  <div>
    <IpsumList :ipsums="ipsums"
      :selected="selectedIpsum"
      :onSelect="handleSelect"
    />
  </div>
</template>

<script>
import ipsumsApi from '../services/data.js';
import IpsumList from './IpsumList.vue';
export default {
  data() {
    return {
      ipsums: ipsumsApi.getIpsums(),
      selectedIpsum: null,
    };
  },
  components: {
    IpsumList
  },
  methods: {
     handleSelect(ipsum) {
       this.selectedIpsum = ipsum;
       console.log(this.selectedIpsum)
     }
   }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
