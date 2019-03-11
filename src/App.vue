<template>
    <div id="app" class="flex flex-col h-screen bg-grey-lighter mx-auto">
        <div class="flex flex-col flex-grow justify-center">
            <div class="font-sans text-lg text-grey-darkest text-center">
                <topic class="my-4"></topic>
                <div class="my-8">
                    <timer v-show="! this.complete" @completed="completed"></timer>
                    <p v-show="this.complete">Congratulations, you have completed five minutes of conversation.</p>
                </div>
            </div>
        </div>
        <div class="flex items-center justify-center bg-grey-light py-8">
            <p class="text-center text-grey-dark text-sm">
                By: <a href="https://nickdown.com" class="no-underline"><span class="italic text-blue">Nick Down</span></a>.
            </p>
        </div>
    </div>
</template>

<script>
    import Timer from './components/Timer.vue';
    import Topic from './components/Topic.vue';

    export default {

        name: 'app',
        components: {
            Timer,
            Topic
        },

        data: function () {
            return {
                complete: false,
            }
        },

        methods: {
            completed: function () {
                this.complete = true;
            }
        }
    }
</script>

<style src="./main.css"></style>
