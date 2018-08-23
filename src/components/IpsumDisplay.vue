<template>
  <section class="display-edit-ipsum">
    <h2>{{ ipsum.title }}</h2>
    <p class="meta">{{ ipsum.category }} | {{ ipsum.author }} | {{ ipsum.authorURL }}
    | {{ ipsum.publishedOn }}</p>
    <p  v-html="ipsum.body"></p>
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

<style scoped>

.meta {
  font-weight: bold;
  font-family: monospace;
  color:#2973b7;
  text-align: center;
}
p {
  text-align: left;
}
</style>