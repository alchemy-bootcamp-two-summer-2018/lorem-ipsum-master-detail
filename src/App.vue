<template>
  <div id="app">
    <Header/>
    <Ipsums/>
  </div>
</template>

<script>
import Header from './components/Header';
import Ipsums from './components/Ipsums';

export default {
  name: 'app',
  // data() {
  //   return 
      
  
  // },
  components: {
    Ipsums,
    Header
    
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
