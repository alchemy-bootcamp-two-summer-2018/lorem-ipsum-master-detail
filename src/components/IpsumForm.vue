<template>
  <form @submit.prevent="handleSubmit">
    <label>Title:
      <input v-model="title" placeholder="enter a title"/>
    </label>
    <label>Category: 
      <input v-model="category" placeholder="enter a category"/>
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
    onCancel: Function,
    onUpdate: Function,
    ipsum: Object
  }




};
</script>

<style scoped>


</style>
