<template>
    <div>
        <p>{{ ipsum.title }}: {{ ipsum.category }}</p>
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
