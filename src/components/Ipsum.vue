<template>
  <div v-if="ipsum">

    <p v-if="!editing">
      <button @click="editing = true">Edit</button>
    </p>

    <IpsumForm 
      v-if="editing"    
      :ipsum="ipsum"
      :onUpdate="handleUpdate"
      :onCancel="handleEndEdit"
    />
    <IpsumDetail 
      v-else
      :ipsum="ipsum"
    />
  </div>
</template>

<script>
import IpsumDetail from './IpsumDetail.vue';
import IpsumForm from './IpsumForm.vue';

export default {
  props: {
    ipsum: Object,
    onUpdate: Function,
  },
  components: {
    IpsumDetail, IpsumForm
  },
  data() {
    return {
      editing: false
    };
  },
  watch: {
    ipsum(newIpsum, oldIpsum) {
      if(newIpsum !== oldIpsum) {
        this.editing = false;
      }
    }
  },
  methods: {
    handleEndEdit() {
      this.editing = false;
    },
    handleUpdate(ipsum) {
      this.onUpdate(ipsum);
      this.handleEndEdit();
    }
  }
};
</script>

<style scoped>


</style>
