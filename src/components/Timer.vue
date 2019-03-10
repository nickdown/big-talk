<template>
    <div>
        <button class="bg-blue hover:bg-blue-dark text-white font-bold py-2 px-4 rounded"
                v-show="! running"
                @click="start">
            Start Timer
        </button>
        <p v-show="running">{{ minutes }} minutes, {{ seconds }} seconds remaining.</p>
    </div>
</template>
<script>
    export default {
        name: "Timer",

        data: function () {
            return {
                running: false,
                time: 300,
                interval: null,
            }
        },

        mounted() {
            this.running = false;
            this.seconds = 5;
            this.interval = null;
        },

        computed: {
            seconds: function () {
                return this.time % 60;
            },

            minutes: function () {
                return Math.floor(this.time / 60);
            }
        },

        methods: {
            start: function () {
                clearInterval(this.interval);
                this.running = true;
                this.interval = setInterval(() => {
                    this.tick();
                }, 1000);
            },

            tick: function () {
                if (this.time <= 1) {
                    this.completed();
                }
                if (this.running) {
                    this.time = this.time - 1;
                }
            },

            completed: function () {
                clearInterval(this.interval);
                this.running = false;
                this.$emit('completed');
            }
        }
    }
</script>
4

<style scoped>

</style>
