<template lang="">
  <div class="result">
    <div class="title">You got sample result 1!</div>
    <div class="desc">Enter a short description here about the result.</div>
  </div>
</template>
<script>
export default {
  props: ['results', 'totalCorrect'],
  computed: {
    resultIndex() {
      let index = 0;

      // loop through results array
      // e = represent the key of the array
      // i = represent the index of the array
      this.results.forEach((e, i) => {
        // if totalCorrect variabel is bigger than e.min and smaller than e.max
        if (e.min <= this.totalCorrect && e.max >= this.totalCorrect) {
          // set the "index" variabel value to index of the array
          index = i;
        }
      });

      return index;
    },
  },
};
</script>
<style lang=""></style>
