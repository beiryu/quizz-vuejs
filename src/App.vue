<template>
  <div id="app">
    <h1>QUIZZ</h1>
    <div v-show="showResult">
      <h3>Your Score {{ point }}</h3>
      <button @click="reset()">Try it again</button>
    </div>
    <div v-show="!showResult">
      <h3>Question {{ indexQ + 1 }} : {{ questions[indexQ].question }} </h3>
      <div v-for="(answer, index) in questions[indexQ].answers" :key="index">
        <input type="radio" name="answer" :value="answer[0]" v-model="answerChosen"> {{ answer }}
      </div>
      <br>
      <button @click="next()" :disabled="answerChosen==''">Next question</button>
    </div>
  </div>
</template>

<script>

export default {
  data() {
		return {
			indexQ: 0,
      questions: [
        {
          question: "Em khong la nang tho? ",
          answers: ['A. Yes', 'B. No'],
          correct: 'A'
        },
        {
          question: "Em khong la nang tho? ",
          answers: ['A. Yes', 'B. No'],
          correct: 'A'
        },
        {
          question: "Em khong la nang tho? ",
          answers: ['A. Yes', 'B. No'],
          correct: 'A'
        },
        {
          question: "Em khong la nang tho? ",
          answers: ['A. Yes', 'B. No'],
          correct: 'A'
        },
        {
          question: "Em khong la nang tho? ",
          answers: ['A. Yes', 'B. No'],
          correct: 'A'
        },
        {
          question: "Em khong la nang tho? ",
          answers: ['A. Yes', 'B. No'],
          correct: 'A'
        },
        {
          question: "Em khong la nang tho? ",
          answers: ['A. Yes', 'B. No'],
          correct: 'A'
        },
        {
          question: "Em khong la nang tho? ",
          answers: ['A. Yes', 'B. No'],
          correct: 'A'
        },
        {
          question: "Em khong la nang tho? ",
          answers: ['A. Yes', 'B. No'],
          correct: 'A'
        },
        {
          question: "Em khong la nang tho? ",
          answers: ['A. Yes', 'B. No'],
          correct: 'A'
        }
      ],
      answerChosen: '',
      showResult: false,
      point: 0
    }
  },
  methods: {
    next: function() {
      if(this.questions[this.indexQ].correct == this.answerChosen) this.point++;
      if(this.indexQ == 9) this.showResult = true;
      else{
        this.indexQ++;
        this.answerChosen = '';
      }    
    },
    reset: function() {
      this.point = 0;
      this.showResult = false;
      this.indexQ = 0;
      this.answerChosen = '';
    }
  }
}
</script>

<style>

</style>
