<template>
  <section class="display-edit-ipsum">
    <h2>{{ ipsum.title }}</h2>
    <p class="meta">{{ ipsum.category }} | {{ ipsum.author }} | {{ ipsum.publishedOn }} | 
      {{ ipsum.authorURL }}</p>
    <p class="body" v-html="ipsum.body"></p>
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



.meta {
  font-weight: bold;
  font-family: monospace;
  color:#2973b7;
  text-align: center !important;
}





</style>