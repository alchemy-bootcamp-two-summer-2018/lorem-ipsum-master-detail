<template>
  <section>
    <h3> {{ ipsum.title }}</h3>
    <p>{{ ipsum.category }}</p>
    <p>{{ ipsum.author }}</p>
    <a :href="ipsum.authorUrl">Visit Author Website</a>
    <p>{{ ipsum.publishedOn }}</p>
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

<style>

</style>
