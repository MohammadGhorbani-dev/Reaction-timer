<script>
export default {
  props: ["score"],
  data() {
    return { rank: null };
  },
  mounted() {
    if (this.score < 311) this.rank = "amazing =)))";
    else if (this.score < 501) this.rank = "good";
    else if (this.score < 801) this.rank = "not bad";
    else this.rank = "you very slow =((";
  },
};
</script>
<template>
  <p>Reaction : {{ score }} ms</p>
  <p>{{ rank }}</p>
</template>
