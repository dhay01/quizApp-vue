<template>

  <div class="single-question" v-for="(question, qi) in questions" :key="question.q"
       v-show="questionsAnswered==qi">
    <div class="question">{{ question.q }}</div>
    <div class="answers" v-for="answer in question.answers" :key="answer.text" @click.prevent="selectAnswer(answer.is_correct)">
      <div class="answer">{{ answer.text }}</div>


    </div>
  </div>

</template>
<script>
export default {
  props: ['questions', 'questionsAnswered'],
  emits: ["answered"],
  methods:{
    selectAnswer(is_correct) {
        this.$emit('answered')
    }

  }
};
</script>
<style>

</style>