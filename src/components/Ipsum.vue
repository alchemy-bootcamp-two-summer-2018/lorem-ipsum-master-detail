<template>
    <div>
        <IpsumDetail :ipsumItem="ipsumItem"/>
    </div>
</template>

<script>
import IpsumDetail from './IpsumDetail.vue';

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
