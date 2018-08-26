<template>
    <li :class="{ selected: ipsum === selected }"
    @click="handleClick"
    >
        <h4>{{ ipsum.title }}</h4>
    </li>
</template>

<script>
export default {
  props: {
    ipsum: Object,
    selected: Object,
    onSelect: Function

  },
  methods: {
    handleClick() {
      this.onSelect(this.ipsum);
    }
  }
};
</script>

<style scopted>
  li {
  list-style: none;
  text-align: center;
  border: 2px solid #aaa;
  box-shadow: 2px 2px 5px #aaa;
}

h4 {
  font-family: sans-serif;
  font-size: 20px;
}

selected:hover {
  background-color: rgb(164, 250, 190)
}

li:hover {
  background-color: rgb(164, 250, 190)
}

.selected {
  background: lightsteelblue;
}
</style>
