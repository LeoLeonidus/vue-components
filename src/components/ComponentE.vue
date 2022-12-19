<template>
    <div>
        <h2>I am Component E and call ComponentF</h2>
        <ComponentF />
    </div>
</template>

<script>
    import ComponentF from './ComponentF.vue'
    export default {
        name: 'ComponentE',
        components: {
            ComponentF
        }
        
    }
</script>

<style scoped>

</style>