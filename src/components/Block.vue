<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTimer: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTimer += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      this.$emit("endGame", this.reactionTimer);
    },
  },
};
</script>
<template>
  <div
    @click="stopTimer"
    v-if="showBlock"
    class="w-64 h-52 flex justify-center items-center mt-12 bg-[#0faf87] rounded-3xl"
  >
    Click Me
  </div>
</template>
