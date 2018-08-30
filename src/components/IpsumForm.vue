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
      key: '',
      title: '',
      body: '',
    };
  },
  created() {
    const ipsum = this.ipsum;
    this.key = ipsum.key;
    this.title = ipsum.title;
    this.body = ipsum.body;

  },
  methods: {
    handleSubmit() {
      const ipsum = {
        key: this.key,
        title: this.title,
        body: this.body,
      };
      this.onUpdate(ipsum);
    }
  }
};
</script>

<style>

</style>
