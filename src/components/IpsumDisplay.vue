<template>
  <section class="display">
    <h2>{{ ipsum.title }}</h2>
    <p class="meta">{{ ipsum.category }} | {{ ipsum.author }} | {{ ipsum.authorURL }}
    | {{ ipsum.publishedOn }}</p>
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

<style scoped>
.display{
  max-width: 700px;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.2), 0 3px 10px 0 rgba(0, 0, 0, 0.19);
  padding: 30px
}
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