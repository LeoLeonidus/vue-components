<template>
    <div>
        <!-- così fa il bind del non props attrinute sull'h2 anziche sul div -->
        <h2 v-bind="$attrs">Article Component</h2>
        <h2>Title - {{title}}</h2>
        <h2>Like - {{like}}</h2>
        <h2>isPublished - {{isPublished}}</h2>
    </div>
</template>

<script>
    export default {
        name: 'ArticleComponent',
        props: {
            title: {
                type:String,
                required:true,
                default: 'Article default value'
            },
            like: Number,
            isPublished: Boolean
        },
        inheritAttrs: false // per evitare che i non props attribute vengano messi sul padre
    }
</script>

<style scoped>

</style>