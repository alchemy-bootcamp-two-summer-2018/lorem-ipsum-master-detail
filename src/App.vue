<template>
  <div id="app">
    <Ipsums/>
  </div>
</template>

<script>
import Ipsums from './components/Ipsums';

export default {
  name: 'app',
  // data() {
  //   return 
      
  
  // },
  components: {
    Ipsums
    
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
