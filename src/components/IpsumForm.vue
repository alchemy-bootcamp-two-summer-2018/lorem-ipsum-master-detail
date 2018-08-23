<template>
    <form @submit.prevent="handleSubmit">
        <p>
            <label>
                Title: <input v-model="title">
            </label>
        </p>
                <p>
            <label>
                Author: <input v-model="author">
            </label>
        </p>
                <p>
            <label>
                Body: <input v-model="body">
            </label>
        </p>
        <button type="submit">Update</button>
        <button type="cancel" @click="onCancel">Cancel</button>
    </form>
</template>

<script>
export default {
    props: {
        ipsum: Object,
        onUpdate: Function, 
        onCancel: Function
    },
    data() {
        return {
            title: '',
            author: '',
            body: ''
        };
    },
    create() {
        const ipsum = {
            key: this.ipsum.key,
            title: this.title,
            author: this.author,
            body: this.body
        }
    },
    methods: {
        handleSubmit() {
            const ipsum = {
                key: this.title,
                title: this.title,
                author: this.author,
                body: this.body
            };
            this.onUpdate(ipsum);
        }
    }
}
</script>

<style>

</style>
