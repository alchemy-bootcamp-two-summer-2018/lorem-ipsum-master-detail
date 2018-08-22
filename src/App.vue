<template>
  <div >
    <Header />
    <Ipsums />
  </div>
</template>

<script>
import Header from './components/Header';
import Ipsums from './components/Ipsums';

export default {
  name: 'app',

  components: {
    Header,
    Ipsums,
  },

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
