<template>
    <div>
        <button v-show="! running" @click="start">Start Timer</button>
        <p v-show="running">{{ seconds }} seconds remaining.</p>
    </div>
</template>
<script>
    export default {
        name: "Timer",

        data: function () {
            return {
                running: false,
                seconds: 0,
                interval: null,
            }
        },

        mounted() {
            this.running = false;
            this.seconds = 5;
            this.interval = null;
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
                if (this.seconds <= 1) {
                    this.completed();
                }
                if (this.running) {
                    this.seconds = this.seconds - 1;
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
