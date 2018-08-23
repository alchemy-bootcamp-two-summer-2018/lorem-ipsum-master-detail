<template>
  <form @submit.prevent="handleSubmit">
   <p>
      <label> <input placeholder="here" v-model="title"></label>
      <button type="submit">Add Your New Ipsum</button>
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


<style scoped>

form {
    border: solid 1px #dddddd;
    padding: 40px;
}

input {
  padding: 10px;
  margin-right: 20px;
  width: 300px;
  font-size:14px;

}

button {
    font-size: 16px;
    background: #42b983;
    width: 250px;
    border-radius: 3px;
    color: white;
    padding: 8px;
    text-transform: uppercase;
    letter-spacing: 2px;
}

</style>