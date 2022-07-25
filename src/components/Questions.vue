<template lang="">
  <div class="questions-ctr">
    <div class="progress">
      <div class="bar"></div>
      <div class="status">{{ questionsAnswered }} out of 3 questions answered</div>
    </div>
    <div class="single-question" v-for="(question, index) in questions" :key="question.q" v-show="questionsAnswered === index">
      <div class="question">{{ question.q }}</div>
      <div class="answers" v-for="answer in question.answers" :key="answer.text" @click.prevent="selectAnswer(answer.is_correct)">
        <div class="answer">{{ answer.text }}</div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ['questions', 'questionsAnswered'],
  methods: {
    selectAnswer(is_correct) {
      this.$emit('question-answered', is_correct);
    },
  },
};
</script>
<style lang=""></style>
