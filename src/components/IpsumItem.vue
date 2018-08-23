<template>
    <li :class="{ selected: ipsum === selected }"
    @click="handleClick"
    >
        <h4>{{ ipsum.title }}</h4>

        <!-- {{ ipsum.body }} -->
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

<style>
  li {
  list-style: none;
  text-align: center;
  border: 1px solid #aaa;
}

.selected {
  background: lightsteelblue;
}
</style>
