<template>
  <form @submit.prevent="handleSubmit">
    <label>Title:
      <input v-model="title" placeholder="enter a title"/>
    </label>
    <label>Category: 
      <input v-model="category" placeholder="enter a category"/>
    </label>
    <label>Body: 
      <textarea v-model="body" placeholder="modify dis body"></textarea>
    </label>
    <button type="submit">
      Update
    </button>
    <button type="cancel" @click="onCancel">
      Cancel
    </button>
  </form>

</template>

<script>
export default {
  props: {
    ipsum: Object,
    onUpdate: Function,
    onCancel: Function,
  },
  data() {
    return {
      title: '',
      category: '',
      body: '',
    };
  },
  created() {
    const ipsum = this.ipsum;
    this.title = ipsum.title;
    this.category = ipsum.category;
    this.body = ipsum.body;
  },
  methods: {
    handleSubmit() {
      const ipsum = {
        key: this.ipsum.key,
        title: this.title,
        category: this.category,
        body: this.body,
      };
      this.onUpdate(ipsum);
    }
  }




};
</script>

<style scoped>
form {
  width: 80%;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}
textarea {
  display: block;
  margin: 0px;
  padding: 20px;
  width: 800px;  
  height: 500px;
  border-radius: 12px;
}
button {
  margin: 10px;
  padding: 5px;
  border-radius: 12px;
}
button:hover {
  cursor: pointer;
  background-color: #eb6624;
}
label {
  font-weight: bold;
  margin: 10px;
}
input {
  height: 29px;
  border-radius: 12px;
  padding: 2px;
}

</style>
