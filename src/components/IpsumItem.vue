<template>
  <li 
    :class="{ selected: ipsum === selected }"
    @click="handleClick"
  >
    <p class="tile-title">{{ ipsum.title }}</p>
    <p class="tile-cat">{{ ipsum.category }}</p>
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
  border: 1px solid rgb(126, 124, 124);
  border-radius: 12px;
  box-shadow: 1px 1px 3px black;
  cursor: pointer;
  background-color: rgb(255, 254, 177);

}

li:hover {
  box-shadow: 2px 2px 5px black;
  background-color: #f78147;
}

.selected {
  background: #eb6624;
}

.tile-title {
  font-weight: bold;
  font-size: 130%;
}
.tile-cat {
  text-transform:capitalize;
}

</style>
