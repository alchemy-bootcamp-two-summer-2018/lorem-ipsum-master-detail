<template>
  <div>
    <section v-if="ipsum">
      <p v-if="!editing">
        <button @click="editing = true">Edit</button>
      </p>
      <IpsumForm v-if="editing" 
        :ipsum="ipsum"
        :onUpdate="handleUpdate"
        :onCancel="handleEndEdit"
      />
      <IpsumDisplay v-else :ipsum="ipsum"/>  
    </section>

    <section v-else>
      <p>Please choose an ipsum</p>
    </section>
  </div>
</template>

<script>
//allows user to view detailed info
// and also edit that info

import IpsumForm from './IpsumForm.vue';
import IpsumDisplay from './IpsumDisplay.vue';

export default {
  props: {
    ipsum: Object,
    onUpdate: Function
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
  components: {
    IpsumForm,
    IpsumDisplay
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

<style>

</style>