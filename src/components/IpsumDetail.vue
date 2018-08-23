<template>
    <section>
        <h3>{{ ipsumItem.title }}</h3>
        <p class="info">Category: {{ ipsumItem.category }}</p>
        <p class="info">Author: {{ ipsumItem.author }}</p>
        <p class="info">Author URL: {{ ipsumItem.authorUrl }}</p>
        <p class="info">Publication Date: {{ ipsumItem.publishedOn }}</p>
        <p class="body" v-html="ipsumItem.body">Body HTML:</p>
    </section>
</template>

<script>
export default {
  props: {
    ipsumItem: Object
  }

};
</script>

<style scoped>

.info {
  margin: 10px;
}

.body {
  text-align: left;
  margin-bottom: 30px;
}


</style>
