<template>
    <div>
        <h2>Edit This Ipsum</h2>
        <form @submit.prevent="handleSubmit">
            <p>Title<br/>
                <label>
                    <input v-model="title">
                </label>
            </p>
            <p>Category<br/>
                <label>
                    <input v-model="category">
                </label>
            </p>
            <p>Author<br/>
                <label>
                    <input v-model="author">
                </label>
            </p>
            <p>Author URL<br/>
                <label>
                    <input v-model="authorUrl">
                </label>
            </p>
            <p>Publication Date<br/>
                <label>
                    <input v-model="publishedOn">
                </label>
            </p>
            <p>Body HTML<br/>
                <label>
                    <textarea v-model="body"></textarea>
                </label>
            </p>
            <p>
                <button type="submit">Update</button>
            </p>
            <p>
                <button type="cancel" @click="onCancel">Cancel</button>
            </p>
        </form>
    </div>  
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

<style scoped>

input {
    width: 70%;
    padding: 10px;
    margin: 5px 20px 20px 20px;
    font-size: 1em;
}

textarea {
    width: 70%;
    height: 200px;
    font-size: 1em;
}

h2 {
    margin: 20px 20px 30px;
}


</style>
