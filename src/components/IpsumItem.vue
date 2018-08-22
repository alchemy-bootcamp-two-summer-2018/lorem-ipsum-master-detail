<template>
    <div>
        <p>Title: {{ ipsum.title }}</p>
        <p>Category: {{ ipsum.category }}</p>
    </div>
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
