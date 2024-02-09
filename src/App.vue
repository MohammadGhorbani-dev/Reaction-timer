<script>
import Block from "./components/Block.vue";
import Result from "./components/Result.vue";
export default {
  name: "App",
  components: { Block, Result },
  data() {
    return {
      delay: null,
      isPlaying: false,
      score: null,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.score = null;
      this.delay = 1000 + Math.random() * 5000;
      console.log(this.delay);
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
    },
  },
};
</script>

<template>
  <div class="h-screen flex flex-col items-center gap-7 pt-10">
    <h1 class="text-center text-3xl">OpneCode Reaction timer</h1>
    <button
      @click="start"
      :disabled="isPlaying"
      class="w-32 h-12 rounded-2xl bg-sky-950"
    >
      Play
    </button>
    <Result v-if="score" :score="score" />
    <Block v-if="isPlaying" :delay="delay" @endGame="endGame" />
  </div>
</template>
