/<template>
    <li :class="{ selcted: ispum === selected}">

        <h3> {{ipsum.title}} This is Ipsum Title </h3>
        <p> {{ipsum.catagory}} This is Ipsum Title </p>

    </li>
</template>

<script>
export default {

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

}
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
