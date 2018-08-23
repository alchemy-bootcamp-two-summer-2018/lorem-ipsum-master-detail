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
  background-color:rgb(139, 220, 230)
}

div:hover {
  background-color: rgb(226, 250, 253);
}

div {
    border: 2px solid rgb(196, 249, 255);
    max-width: 500px;
    background-color: white;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: rgb(58, 75, 172);
    padding: 10px;
}
</style>
