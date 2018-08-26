<template>
    <form @submit.prevent="handleAdd">
        <h2>Got your own ideas for an Ipsum?</h2>
        <p>
            <label>
                Title: <input v-model="title">
            </label>
        </p>
        <p>
            <label>
                Body: <input v-model="body">
            </label>
        </p>
        <button type="submit">Add</button>
        
    </form>
</template>

<script>
export default {
    props: {
        ipsum: Object,
        onAdd: Function
    },
    data () {
        return {
            title: '',
            body: ''
        };
    },
    methods: {
        handleAdd() {
            const ipsum = {
                key: this.title,
                title: this.title,
                body: this.body

            };
            this.onAdd(ipsum);
        }
    }
};
</script>

<style>

</style>
