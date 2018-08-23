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
        <button type="cancel" @click="onCancel">Cancel</button>
    </form>  
</template>

<script>
export default {
  props: {
    ipsumItem: Object,
    onUpdate: Function,
    onCancel: Function
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
  created() {
    const ipsumItem = this.ipsumItem;
    this.title = ipsumItem.title;
    this.category = ipsumItem.category;
    this.author = ipsumItem.author;
    this.authorUrl = ipsumItem.authorUrl;
    this.publishedOn = ipsumItem.publishedOn;
    this.body = ipsumItem.body;
  },
  methods: {
    handleSubmit() {
      const ipsumItem = {
        title: this.title,
        category: this.category,
        author: this.author,
        authorUrl: this.authorUrl,
        publishedOn: this.publishedOn,
        body: this.body
      };
      this.onUpdate(ipsumItem);
    }
  }
};
</script>

<style>

</style>
