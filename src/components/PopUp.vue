<template>
    <!-- Custom Events per passare proprietà dal child al parent component -->
    <div>
        <h3>PopUp Component - Custom Events per passare proprietà dal child al parent component</h3>
        <input type="text" v-model="name" />
        <button @click="$emit('close' , name)">Close</button>
    </div>
</template>

<script>
    export default {
        name: 'PopUp',
        emits: { //custom event da passare al parent
            close: (name) => {
                if(! name){
                    return false
                } else {
                    return true
                }
            }
        },
        data(){
            return {
                name: ''
            }
        }
    }
</script>

<style scoped>

</style>