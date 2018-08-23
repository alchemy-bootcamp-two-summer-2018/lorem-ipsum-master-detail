<template>
    <div>
      <section v-if="ipsum">
        <p v-if="!editing">
          <button @click="editing = true"> Edit</button>
        </p>
        <IpsumForm v-if="editing"
          :ipsum="ipsum"
          :onUpdate="handleUpdate"
          :onCancel="handleEndEdit"
        />
        <IpsumDisplay 
          :ipsum="ipsum"
        />
      </section>

      <section>
          <p>Please Choose an Ipsum</p>
      </section>


    </div>
</template>

<script>
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
