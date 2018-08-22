<template>
    <section>
        <h3>{{ ipsumItem.title }}</h3>
        <p>{{ ipsumItem.category }}</p>
        <p>{{ ipsumItem.author }}</p>
        <p>{{ ipsumItem.authorUrl }}</p>
        <p>{{ ipsumItem.publishedOn }}</p>
        <p v-html="ipsumItem.body"></p>
    </section>
</template>

<script>
export default {
  props: {
    ipsumItem: Object
  }

};
</script>

<style>

</style>
