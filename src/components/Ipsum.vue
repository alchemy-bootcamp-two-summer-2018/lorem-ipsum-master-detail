<template>
  <div class="flex-container">
    <section v-if="ipsum">
      <IpsumForm v-if="editing" 
        :ipsum="ipsum"
        :onUpdate="handleUpdate"
        :onCancel="handleEndEdit"
      />
      <IpsumDisplay v-else :ipsum="ipsum"/>  
      
      <p v-if="!editing">
        <button @click="editing = true">Edit</button>
      </p>
    </section>

    <section v-else>
      <p></p>
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
.flex-container{
  display: flex;
  justify-content: center;
}

</style>