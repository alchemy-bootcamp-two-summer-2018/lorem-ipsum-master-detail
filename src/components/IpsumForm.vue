<template>
    <form @submit.prevent="handleSubmit">
        <p>
            <label>
                Title: <input v-model="title">
            </label>
        </p>
        <p>
            <label>
                Body: <input v-model="body">
            </label>
        </p>
        <!-- <input v-html="ipsum.body"> -->
        <button type="submit">Update</button>
        <button type="cancel" @click="onCancel">Cancel</button>
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
      body: '',
    };
  },
  created() {
    const ipsum = this.ipsum;
    this.title = ipsum.title;
    //   author: this.author,
    this.body = ipsum.body;
    
  },
  methods: {
    handleSubmit() {
      const ipsum = {
        key: this.title,
        title: this.title,
        // author: this.author,
        body: this.body,
        
      };
      this.onUpdate(ipsum);
    }
  }
};
</script>

<style>

</style>
