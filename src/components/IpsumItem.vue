<template>
  <li 
    :class="{ selected: ipsum === selected }"
    @click="handleClick"
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
    selected: Object
  },
  methods: {
    handleClick() {
      this.onSelect(this.ipsum);
      console.log('ipsum selected', this.ipsum);
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
.selected {
  background: red;
}

</style>
