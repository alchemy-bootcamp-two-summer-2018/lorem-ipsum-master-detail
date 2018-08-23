<template>
  <div v-if="ipsum">
    <IpsumForm v-if="editing"    
      :ipsum="ipsum"
      :onUpdate="handleUpdate"
      :onCancel="handleEndEdit"
    />
    <IpsumDetail v-else    />
  </div>
</template>

<script>
import IpsumDetail from './IpsumDetail.vue';
import IpsumForm from './IpsumForm.vue';

export default {
  props: {
    onUpdate: Function,
    ipsum: Object,
    selected: Object
  },
  components: {
    IpsumDetail, IpsumForm
  },
  data() {
    return {
      editing: false
    };
  }
};
</script>

<style scoped>


</style>
