<template>
    <form @submit.prevent="handleSubmit">
        <label>
            Add New Title: <input v-model="title">
        </label>
        <p>
            <button>Add</button>
        </p>
    </form>
</template>

<script>
export default {
    props: {
        onAdd: Function
    },
    data() {
        return {
            title: '',
            category: '',
            author: '',
            authorUrl: '',
            publishedOn: '',
            body: ''
        }
    },
    methods: {
        handleSubmit() {
            const newIpsum = {
                title: this.title,
                category: '',
                author: '',
                authorUrl: '',
                publishedOn: '',
                body: ''
            };
            this.onAdd(newIpsum);
            
            this.title = '';
        }
    }


};
</script>

<style>

</style>
