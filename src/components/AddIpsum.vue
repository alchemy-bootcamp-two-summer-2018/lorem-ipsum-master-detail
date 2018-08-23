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
