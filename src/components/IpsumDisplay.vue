<template>
  <section>
    <h3>{{ ipsum.title }}</h3>
    <p>{{ ipsum.category }}</p>
    <p>{{ ipsum.author }}</p>
    <p>{{ ipsum.authorURL }}</p>
    <p>{{ ipsum.publishedOn }}</p>
    <p>{{ ipsum.body }}</p>
  </section>
</template>

<script>
//detailed view of each ipsum

export default {
  props: {
    ipsum: Object
  }
};

</script>

<style>

</style>