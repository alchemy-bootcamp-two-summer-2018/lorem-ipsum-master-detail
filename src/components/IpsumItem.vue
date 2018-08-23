/<template>
    <li :class="{ selected: ipsum === selected}"
    @click="handleClick"
    >
        <h3> Title: {{ipsum.title}} </h3>
        <p> Category: {{ipsum.category}} </p>
    </li>
</template>

<script>
export default {

// displays category and title for a single ipsum 

  props: {
    ipsum: Object,
    selected: Object,
    onSelect: Function
  },

  methods: {
    handleClick(){
      this.onSelect(this.ipsum);
    }
  }

};
</script>

<style>

.selected {
    background: pink;
}

li {
    background: grey;
    list-style:none;
    border: solid 1px black;
}

</style>
