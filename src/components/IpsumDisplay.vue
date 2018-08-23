<template>
    <section>
        <span v-if="ipsum"
         v-html="ipsum.body"></span>

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
