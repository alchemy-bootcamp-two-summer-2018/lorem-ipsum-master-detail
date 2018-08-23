<template>
  <section>
    <h3>{{ ipsum.title }}</h3>
    <p class="category">Category: {{ ipsum.category }}</p>
    <div v-html="ipsum.body" class="body"></div>
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

}
.body {
  margin: 50px;
}
.body p {
  margin: 50px;
}
.body p img {
  display: block;
}


</style>
