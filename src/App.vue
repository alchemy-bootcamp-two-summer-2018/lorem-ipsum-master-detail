<template>
  <div >
    <Header />
    <Ipsums 
    :ipsums="ipsums"
    :selected="selectedIpsum"
    :onSelect="handleSelect"
    />
  </div>
</template>

<script>
import Header from './components/Header';
import Ipsums from './components/Ipsums';
import ipsumApi from './services/ipsumApi';

export default {
  name: 'app',

  // data(){
  //   return {
  //     ipsums: ipsumApi.getIpsums(),
  //     selectedIpsum: null
  //   };
  // },
  
  components: {
    Header,
    Ipsums,
  },

  // methods:{

  //   handleSelect(ipsum) {
  //     this.selectedIpsum = ipsum;

  //   },
  //   handleUpdate(updated) {
  //     const index = this.ipsums.findIndex(ipsum => {
  //       return ipsum.title === updated.title; //key?
  //     });
  //     if(index !== -1) {
  //       this.ipsums.splice(index, 1, updated);
  //       this.selectedIpsum = updated;
  //     }
  //   }
  // }
};
</script>

<style>
* {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
