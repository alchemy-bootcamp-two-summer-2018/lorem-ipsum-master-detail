<template>
    <div id="ipsumViewer">
      <article v-if="ipsumItem">
        <IpsumForm/>
        <IpsumDetail :ipsumItem="ipsumItem"/>
      </article>
      <p v-else>Please select an ipsum</p>
    </div>
</template>

<script>
import IpsumDetail from './IpsumDetail.vue';
import IpsumForm from './IpsumForm.vue';

export default {
  props: {
    ipsumItem: Object
  },
  components: {
    IpsumDetail
  }
};
</script>

<style>

</style>
