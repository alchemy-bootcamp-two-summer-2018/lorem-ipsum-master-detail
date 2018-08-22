<template>
  <li 
    class="tile"
    @select="onSelect"
  >
    <p>{{ ipsum.title }}</p>
    <p>{{ ipsum.category }}</p>
  </li>
</template>


<script>
export default {
  props: {
    ipsum: Object,
    onSelect: Function,
  },
  methods: {
    handleClick() {
      this.onSelect(this.animal);
    }
  }
  
};


</script>

<style scoped>

li {
  list-style: none;
  text-align: center;
  border: 1px solid #aaa;
}

</style>
