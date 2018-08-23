<template>
    <div class="list-area">
        <h2>Select an Ipsum to See Detail</h2>
        <div class="list">
          <IpsumItem v-for="ipsum in ipsums"
              :key="ipsum.title"
              :ipsum="ipsum"
              :selected="selected"
              :onSelect="onSelect"/>
        </div>
    </div>
</template>

<script>
import IpsumItem from './IpsumItem.vue';

export default {
  props: {
    ipsums: Array,
    onSelect: Function,
    selected: Object
  },
  components: {
    IpsumItem
  }
};

</script>

<style scoped>

  .list-area {
    margin: 30px;
  }

  .list {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(300px, 2fr));
      grid-gap: 20px;
      border: 2px solid rgb(32, 44, 94);
      padding: 30px;
  }

  h2 {
    padding: 20px 20px 30px;
    background-color: #DEF9FD;
    border-top: 2px solid rgb(32, 44, 94);
    border-left: 2px solid rgb(32, 44, 94);
    border-right: 2px solid rgb(32, 44, 94);
  }

      
</style>
