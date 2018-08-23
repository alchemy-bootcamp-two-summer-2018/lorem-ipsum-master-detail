<template>
  <section class="display-edit-ipsum">
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

<<<<<<< HEAD
<style>
img {display: block; 
    text-align: center;
    margin-left: auto;
    margin-right: auto;
    width: 25%;}
=======
<style scoped>
>>>>>>> 1936bf40ee3400e3847827dd27add0607e203fc6

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