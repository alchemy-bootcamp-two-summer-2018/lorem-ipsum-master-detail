<template>
  <form @submit.prevent="onAdd">
    <label>Title:
      <input v-model="title"/>
    </label>
    <label>Category: 
      <input v-model="category"/>
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
    onAdd: Function,
    onCancel: Function,
    ipsum: Object
  },
  created() {
    const ipsum = this.ipsum;
    this.title = ipsum.title;
    this.category = ipsum.category;
    console.log('testing created');
  }

};
</script>

<style scoped>


</style>
