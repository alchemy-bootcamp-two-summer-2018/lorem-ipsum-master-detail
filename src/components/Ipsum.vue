<template>
    <div>
        <section>
            <IpsumDisplay 
            :ipsum="ipsum"
            />
        </section>
    </div>
</template>

<script>
import IpsumDisplay from './IpsumDisplay.vue';

export default {
  props: {
    ipsum: Object,
    ipsums: Array,
  },
  components: {
    IpsumDisplay
  },

};
</script>

<style>

</style>
