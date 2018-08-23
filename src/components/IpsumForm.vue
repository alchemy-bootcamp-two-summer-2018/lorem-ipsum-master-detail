<template>
  <form class="display-edit-ipsum" @submit.prevent="handleSubmit">
    <h2> Edit Ipsum Below </h2>
    <p>
      <label>
          <p>
          Title: 
          </p>
          <input v-model="title">
      </label>
    </p>
    <p>
      <label>
        <p> 
        Category:
        </p> 
        <input v-model="category">
      </label>
    </p>
    <p>
      <label>
        <p>
        Author: 
        </p>
        <input v-model.number="author">
      </label>
    </p>
    <p>
      <label>
        <p>
        AuthorURL: 
        </p>
        <input v-model.number="authorUrl">
      </label>
    </p>
    <p>
      <label>
        <p>
        Published On: 
        </p>
        <input v-model.number="publishedOn">
      </label>
    </p>
    <p>
      <label>
        <p>
        Body: 
        </p>
        <textarea v-model="body"></textarea>
      </label>
    </p>
    <p>
      <button type="submit">Update</button>
      <button type="cancel" @click="onCancel">Cancel</button>
    </p>
  </form>
</template>

<script>
//allows user to edit ipsum info

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

<style scoped>
p {
  text-align: left;
  margin: 0;
}

form {
 
  padding: 40px;
}

input {
  padding: 20px;
  min-width: 570px;
  margin-bottom: 15px;
  text-align: left;
  border: solid 1px #dddddd;

}

textarea {
  padding: 20px;
  min-width: 570px;
  min-height: 250px;
  margin-bottom: 15px;
  text-align: left;
  border: solid 1px #dddddd;

}

</style>