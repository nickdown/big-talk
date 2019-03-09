<template>
    <h3>Topic to Discuss: {{ topic }}</h3>
</template>

<script>
    export default {
        name: "Topic",

        data: function () {
            return {
                topics: [],
            }
        },

        mounted () {
            this.topics = [
                'best food',
                'alcohol',
                'school',
                'the weather',
            ]
        },

        computed: {
            topic: function () {
                return this.topics[Math.floor(Math.random()*this.topics.length)];
            }
        },
    }
</script>

<style scoped>

</style>
