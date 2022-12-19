<template>
    <div>
        <h2>Here is ComponentF</h2>
        <h3>User Name come from App and is {{userName}}</h3>
    </div>
</template>

<script>
    export default {
        name: 'ComponentF',
        inject: ['userName']
    }
</script>

<style scoped>

</style>