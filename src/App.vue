<template>
  <div id="app">
    <h1>Five Minutes of Conversation</h1>
    <topic></topic>
    <timer v-show="! this.complete" @completed="completed"></timer>
    <p v-show="this.complete">Congratulations, you have completed five minutes of conversation.</p>
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

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
