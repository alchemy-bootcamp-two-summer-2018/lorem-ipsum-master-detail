<template>
  <section>
    <h3>{{ ipsum.title }}</h3>
    <p class="category">Category: {{ ipsum.category }}</p>
    <div v-html="ipsum.body" class="ipsum-body"></div>
  </section>
</template>

<script>
export default {
  props: {
    ipsum: Object
  }
};

</script>

<style scoped>

h3 {
  font-size: 48px;
}
.category {
  font-style: oblique;
  margin: 8px;
}


</style>
