<template>
  <div id="app">
    <Ipsums:
      :ipsums="ipsums"
      :selected="selectedIpsum"
      :onselect="handleSelect"
      />
  <IpsumViewer
    :ipsum="selectedIpsum"
    :onUpdate="handleUpdate"
    />
</template>

<script>
import ipsumsApi from './services/ipsumsApi';

export default {
  name: 'app',
  data() {
    return 
  
  }
  components: {
    
  }
}
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
