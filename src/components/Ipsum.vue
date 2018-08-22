<template>
  <div>
    <IpsumDetail/>
    <IpsumForm/>
  </div>
</template>

<script>
import IpsumDetail from './IpsumDetail.vue';
import IpsumForm from './IpsumForm.vue';

export default {
  props: {
    onUpdate: Function,
    ipsum: Object
  },
  components: {
    IpsumDetail, IpsumForm
  }

};
</script>

<style scoped>


</style>
