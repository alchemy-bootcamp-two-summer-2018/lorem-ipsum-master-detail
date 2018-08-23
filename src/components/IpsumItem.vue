<template>
    <div :class="{ selected: ipsum === selected }"
      @click="handleClick">
        <p>{{ ipsum.title }}: {{ ipsum.category }}</p>
    </div>
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
    }
  }
};
</script>

<style scoped>

.selected {
  border: 1px solid black;
}
</style>
