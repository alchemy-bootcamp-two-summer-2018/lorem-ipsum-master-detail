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

//this form allows a user to add a new ipsum title...
//then they can add in the other info separately in the other form


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
      
      // add new user ipsum to list of ipsums
      this.onAdd(newIpsum);

      this.title = '';
    }
  }
};

</script>

<style>

</style>