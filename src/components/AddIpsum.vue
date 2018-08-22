<template>
    <form @submit.prevent="handleSubmit">
        <label>
            title: <input v-model="title">
        </label>
        <label>
            category: <input v-model="category">
        </label>
        <label>
            author: <input v-model="author">
        </label>
        <label>
            authorUrl: <input v-model="authorUrl">
        </label>
        <label>
            publishedOn: <input v-model="publishedOn">
        </label>
        <label>
            body: <input v-model="body">
        </label>
        <button type="submit">Update</button>
    </form>
</template>

<script>
export default {
  props: {
    onUpdate: Function
  },
  methods: {
    handleSubmit() {
      const ipsum = {
        title: this.title,
        category: this.category,
        author: this.author,
        authorUrl: this.authorUrl,
        publishedOn: this.publishedOn,
        body: this.body
      };
      this.onUpdate(ipsum);
    }
  }
};
</script>

<style>

</style>
