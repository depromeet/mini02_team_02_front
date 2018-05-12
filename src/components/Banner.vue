<template>
<div class="banner">
  <h1>
    대중교통을 이용하다가 잃어버린 물건이 있나요?
  </h1>
  <p>
    버스, 지하철,  택시 등 대중교통 이용 중 잃어버린 물건을 찾을 수 있도록 도와드립니다.
    물건을 잃어버리거나 분실물을 습득하신 경우 제보해 주세요.
  </p>
  <div class="question" :class="{ active: active }" v-show="!active" @mouseover="questionHover">
    <Question />
  </div>
  <div class="question questionHover" :class="{ active: !active }" v-show="active" @mouseleave="questionHover">
    <QuestionHover />
  </div>
  <Main class="main" />
</div>
</template>

<script>
import Question from '@/assets/img_question.svg';
import QuestionHover from '@/assets/img_question_hover.svg';
import Main from '@/assets/img_main.svg';

export default {
  components: {
    Question,
    QuestionHover,
    Main,
  },
  data() {
    return {
      active: false,
    };
  },
  methods: {
    questionHover: function() {
      console.log('a')
      this.active = !this.active;   
    }
  }
};
</script>

<style scoped>
.banner {
  height: 781px;
  background: #cae4d7;
  margin-top: -120px;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
}
h1 {
  margin-top: 200px;
  font-size: 49.5px;
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 1.38;
  letter-spacing: normal;
  text-align: center;
  color: #333333;
}
p {
  width: 650px;
  font-size: 19px;
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 1.79;
  letter-spacing: normal;
  text-align: center;
  color: #333333;
  margin-bottom: 100px;
}
.main {
  margin-bottom: -200px;
}
.question {
  z-index: 100;
  position: absolute;
  bottom: 50px;
  cursor: pointer;
}
.question.active {
  transform: rotateY(180deg);
  transition: 0.6s;
}
</style>
