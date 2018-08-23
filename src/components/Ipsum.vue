<template>
    <div>
      <section v-if="ipsumItem">
          <p v-if="!editing">
            <button @click="editing = true">Edit</button>
          </p>

        <IpsumForm v-if="editing"
            :ipsumItem="ipsumItem"
            :onUpdate="handleUpdate"
            :onCancel="handleEdit"
        />
        <IpsumDetail v-else :ipsumItem="ipsumItem"/>
      </section>
      <section v-else>
        <p>Please select an ipsum</p>
      </section>
    </div>
</template>

<script>
import IpsumDetail from './IpsumDetail.vue';
import IpsumForm from './IpsumForm.vue';

export default {
  props: {
    ipsumItem: Object,
    onUpdate: Function
  },
  data() {
    return {
      editing: false
    };
  },
  watch: {
    ipsumItem(newIpsumItem, oldIpsumItem) {
      if(newIpsumItem !== oldIpsumItem) {
        this.editing = false;
      }
    }
  },
  components: {
    IpsumDetail,
    IpsumForm
  },
  methods: {
    handleEdit() {
      this.editing = false;
    },
    handleUpdate(ipsumItem) {
      this.onUpdate(ipsumItem);
      this.handleEdit();
    }
  }
};
</script>

<style>

</style>
