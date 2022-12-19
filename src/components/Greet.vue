<template>
    <div>
        <h2>Hello {{name}} aka {{heroName}}</h2>
    </div>
</template>

<script>
    export default {
        name: 'GreetComponent',
        props:['name','heroName']
    }
</script>

<style scoped>

</style>