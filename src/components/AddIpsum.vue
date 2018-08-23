<template>
  <form @submit.prevent="handleSubmit">
    <label>Title:
      <input v-model="title" placeholder="enter a title"/>
    </label>
    <label>Category: 
      <input v-model="category" placeholder="enter a category"/>
    </label>
    <button type="submit">
      Add
    </button>
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
    };
  },
  methods: {
    handleSubmit() {
      const newIpsum = {
        title: this.title,
        category: this.category,

      };
      this.onAdd(newIpsum);      
      this.title = '';
      this.category = '';
    }
  }


};
</script>

<style scoped>
button {
  margin: 10px;
  padding: 8px;
  border-radius: 12px;
  background-color: rgb(247, 212, 138);
  box-shadow: 1px 1px 3px grey;
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
  height: 17px;
  border-radius: 12px;
  padding: 8px 16px;
}


</style>
