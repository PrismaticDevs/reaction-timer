<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">GO</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Results v-if="showResults" :score="score" />
  <Wait v-if="wait" />
</template>

<script>
import Block from "./components/Block.vue";
import Results from "./components/Results.vue";
import Wait from "./components/Wait.vue";

import("./assets/global.css");
import "./assets/global.css";

export default {
  name: "App",
  components: { Block, Results, Wait },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
      wait: false,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResults = false;
      this.wait = true;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
      this.wait = false;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #868686;
  margin-top: 60px;
}

button {
  background: green;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}

button[disabled] {
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
