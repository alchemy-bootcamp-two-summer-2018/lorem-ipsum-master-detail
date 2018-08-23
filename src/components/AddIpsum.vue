<template>
  <form @submit.prevent="handleSubmit">
    <p>
      <label>
        Add a new Ipsum title: <input v-model="title">
      </label>
    </p>
    <p>
      
    <p>
      <button type="submit">Add</button>

    </p>
  </form>
</template>

<script>
export default {
  props: {
    onAdd: Function,
  },
  data() {
    return {
      title: '',
      category: '',
      author: '',
      authorUrl: '',
      publishedOn: '',
      body: ''
    };
  },
  methods: {
    handleSubmit() {
      const newIpsum = {
        title: this.title,
        category: this.category,
        author: this.author,
        authorUrl: this.authorUrl,
        publishedOn: this.publishedOn,
        body: this.body
      };
      this.onAdd(newIpsum);

      this.title = '';
    }
  }
};

</script>

<style>

</style>