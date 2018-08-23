<template>
  <form @submit.prevent="handleSubmit">
    <p>
      <label>
        Title: <input v-model="title">
      </label>
    </p>
     <p>
      <label>
        category: <input v-model="category">
      </label>
    </p>
     <p>
      <label>
        author: <input v-model="author">
      </label>
    </p>
     <p>
      <label>
        authorUrl: <input v-model="authorUrl">
      </label>
    </p>
     <p>
      <label>
        publishedOn: <input v-model="publishedOn">
      </label>
    </p>
     <p>
      <label>
        body: <textarea v-model="body"></textarea>
      </label>
    </p>
    <p>
      <button type="submit">Update</button>
      <button type="cancel" @click="onCancel">Cancel</button>
    </p>
  </form>
    
</template>

<script>
export default {
  props: {
    ipsum: Object,
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
    const ipsum = this.ipsum;
    this.title = ipsum.title;
    this.category = ipsum.category;
    this.author = ipsum.author;
    this.authorUrl = ipsum.authorUrl;
    this.publishedOn = ipsum.publishedOn;
    this.body = ipsum.body;
  },
  methods: {
    handleSubmit() {
      const ipsum = {
        key: this.ipsum.key,
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
