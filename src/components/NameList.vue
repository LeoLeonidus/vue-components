<template>
    <h3 v-for="name in names" v-bind:key="name.fistName">
        <slot v-bind:firstName="name.firstName" :lastName="name.lastName"></slot>
    </h3>
</template>

<script>
    export default {
        name:'NameList',
        data(){
            return {
                names: [
                    {
                        firstName:'Mario',
                        lastName:'Rossi'
                    },
                    {
                        firstName: 'Giulio',
                        lastName: 'Verdi'
                    },
                    {
                        firstName: 'Roberto',
                        lastName: 'Gialli'
                    }
                ]
            }
        }
    }
</script>

<style scoped>

</style>