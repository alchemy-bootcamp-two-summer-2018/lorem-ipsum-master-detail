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
</style>
