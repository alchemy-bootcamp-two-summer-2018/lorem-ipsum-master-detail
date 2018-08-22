<template>
  <div >
    <Ipsums 
    :ipsums="ipsums"
    :selected="selectedIpsum"
    :onSelect="handleSelect"
    />
   
  </div>
</template>

<script>
import Ipsums from './components/Ipsums';
import ipsumApi from './services/ipsumApi';

export default {
  name: 'app',
  components: {
    Ipsums,
  },

  data(){
    return {
      ipsums: ipsumApi.getIpsums(),
      selectedIpsum: null
    };
  },

  methods:{

    handleSelect(ipsum) {
      this.selectedIpsum = ipsum;

    }
  }
};
</script>

<style>
* {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
