<template>
  <div>
    <IpsumList :ipsums="ipsums"
      :selected="selectedIpsum"
      :onSelect="handleSelect"
    />
    <IpsumViewer
    :ipsum="selectedIpsum"
    :onUpdate="handleUpdate"/>

  </div>
</template>

<script>
import ipsumsApi from '../services/data.js';
import IpsumList from './IpsumList.vue';
import IpsumViewer from './IpsumViewer';

export default {
  data() {
    return {
      ipsums: ipsumsApi.getIpsums(),
      selectedIpsum: null,
    };
  },
  components: {
    IpsumList,
    IpsumViewer
  },
  methods: {
    handleSelect(ipsum) {
      this.selectedIpsum = ipsum;
      console.log(this.selectedIpsum);
    },
    handleUpdate(updated) {
      const index = this.ipsums.findIndex(ipsum => {
        return ipsum.key === updated.key;
      });

      if(index !== -1) {
        this.ipsums.splice(index, 1, updated);
        this.selectedIpsum = updated;
      }
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
