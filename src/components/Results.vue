<template>
  <p>Reaction Time: {{ score }} ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 250) {
      this.rank = "Sweeps em off their feet!!!";
    } else if (this.score < 400) {
      this.rank = "Rapid Reflexes";
    } else if (this.score < 500) {
      this.rank = "Borderline Slow";
    } else {
      this.rank = "Snail Pace";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4em;
  color: pink;
  font-weight: bold;
}
</style>