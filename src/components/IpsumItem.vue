/<template>
  <li 
    :class="{ selected: ipsum === selected }"
    @click="handleClick"
    >
        <h2> {{ipsum.title}} </h2>
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

<style scoped>

.selected { 
    background: #35495e;
}
.selected:hover { 
    background: #35495ecf;
}

.selected h2 {
  color: #f8f8f8;
  margin: 0;
  text-align: center;
}

.selected p {
  color: #f8f8f8;
}
h2 {
   margin: 0;
}
p {
  font-family: monospace;
  color:#2973b7;
   margin: 0;
}
li:hover{
  background:#f4f2f2
}
li {
  padding: 20px;
    background: #f8f8f8;
    list-style:none;

    border-radius: 5px;

}

</style>
