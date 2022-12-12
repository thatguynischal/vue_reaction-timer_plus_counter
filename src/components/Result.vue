<template>
  <p>Your Time is : {{ apple }} ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ["apple"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.apple < 250) {
      this.rank = "You're super fast BOIIIII";
    } else if (this.apple < 400) {
      this.rank = "You're pretty fast BOIII";
    } else {
      this.rank = "You're a snail BOI";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4em;
  color: #0faf87;
  font-weight: bold;
}
</style>
