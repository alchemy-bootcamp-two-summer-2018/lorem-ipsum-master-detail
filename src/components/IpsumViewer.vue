<template>
    <div> 
        <section>
          <IpsumDetail :ipsum="ipsum"/>
        </section>
    </div>
</template>

<script>
import IpsumDetail from './IpsumDetail.vue';
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
    IpsumDetail
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
