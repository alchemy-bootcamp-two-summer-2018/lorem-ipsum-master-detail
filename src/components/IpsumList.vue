<template>
    <ul>
        <IpsumItem/>
    </ul>
</template>

<script>
    import IpsumItem from './IpsumItem.vue';

export default {
    props: {
        ipsums: Array
    },
    components: {
        IpsumItem
    }
}
</script>

<style>

</style>
