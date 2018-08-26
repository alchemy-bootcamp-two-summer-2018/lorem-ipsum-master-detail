<template>
  <div class="app">
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

.app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #263d53;
  margin-top: 60px;
  margin: 0;
  height: 100%;
}

button:hover {
  background-color: rgb(164, 250, 190)  
}
button {
  background-color: rgb(231, 238, 247);
  font-size: 24px;
  border-radius: 15px;
  padding: 5px 5px;
}
</style>
