<template>
    <div>
        <input type="text" v-bind:value="modelValue" v-on:input="$emit('update:modelValue',$event.target.value)"/>
    </div>
</template>

<script>
    export default {
        name: 'InputComponent',
        props: {
            modelValue: String
        }
    }
</script>

<style scoped>
input[type="text"] {
    display: block;
    width: 400px;
    padding: 6px 12px;
    font-size: 14px;
    color: #555;
    background-color: #fff;
    background-image: none;
    border: 1px solid #CCC;
    border-radius: 4px;
}
</style>