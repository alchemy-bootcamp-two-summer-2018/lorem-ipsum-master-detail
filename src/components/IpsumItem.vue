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
  padding: 5px 0px;
  list-style: none;
  text-align: center;
  border: 1px solid #aaa;
  border-radius: 12px;
}
.selected {
  background: #eb6624;
}

</style>
