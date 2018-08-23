<template>
  <section>
    <h3>{{ ipsum.name }}</h3>
    <p>{{ ipsum.category }}</p>
    <p v-html="ipsum.body"></p>
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


</style>
