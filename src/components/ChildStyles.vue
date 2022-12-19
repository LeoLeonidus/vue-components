<template>
    <div>
        <slot></slot>
        <h4>ChildStyles Text out of the slot</h4>
    </div>
</template>

<script>
    export default {
        name:'ChildStyles'
    }
</script>

<style scoped>
h4 {
    color: red;
}
</style>