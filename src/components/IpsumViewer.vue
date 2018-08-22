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
        <IpsumDetail v-else :ipsum="ipsum"/>
      </section>

      <section v-else>
          <p> Choose an Ipsum </p>
      </section>

    </div>
</template>

<script>
import IpsumDetail from './IpsumDetail.vue';
import IpsumForm from './IpsumForm.vue';
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
  components: {
    IpsumDetail,
    IpsumForm
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
