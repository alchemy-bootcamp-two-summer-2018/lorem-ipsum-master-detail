<template>
    <div>
        <IpsumList :ipsums="ipsums"/>
    </div>
</template>

<script>
    import ipsums from '../services/ipsumsApi.js'
    import IpsumList from './IpsumList.vue'
export default {
    data: {
        return: {
            ipsums: ipsums
        }
    },
    components: {
        IpsumList
    }
}
</script>

<style>

</style>
