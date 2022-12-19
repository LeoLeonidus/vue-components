<template>
    <div>
        <h2>Component C - call Component E</h2>
        <ComponentE />
    </div>
</template>

<script>

    import ComponentE from './ComponentE.vue'
    export default {
        name: 'ComponentC',
        components: {
            ComponentE
        }
        
    }
</script>

<style scoped>

</style>