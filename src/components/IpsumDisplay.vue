<template>
    <section>
        <span v-if="!editing"
          v-html="ipsum.body"
        >
        </span>

    </section>
</template>

<script>
export default {
  props: {
    ipsum: Object,
    editing: Boolean
  }

};
</script>

<style>
img {
  width: 150px;
}
</style>
