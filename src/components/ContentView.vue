
<template>
  <section>
    <div>A/S 만족도 설문</div>
    <div>
      홍길동 고객님 2023년 10월 25일 차량 A/S 수리는 잘 받으셨나요? 차량 수리에 대한 만족도 설문을 요청 드립니다.<br>
      설문 결과는 더 나은 서비스를 위한 기초 자료로 사용할 예정입니다. 감사합니다.
    </div>
    <div class="questionContain">
      <p>{{ questionTitle }}</p>
      <ul class="questions" v-for="questions in questionList" :key="questions.id">
        <li>
          <input type="radio" value=""> <span v-text="questions.text"></span>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
  export default {
    data: () => ({
      questionList: [
        { text: '매우 상세하게 설명' },
        { text: '비교적 상세하게 설명' },
        { text: '일반적으로 설명' },
        { text: '대충 설명함' },
        { text: '설명 안함' },
      ],
      questionTitle: '1. 수리기사는 수리 내용에 대해 상세하게 설명해 주었나요?',
    }),
    methods: {

    }
  }
</script>

<style scoped>
  section {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    margin: 40px auto 80px;
    width: 1150px;
    font-size: 1.25rem;
  }
  section > div {
    margin-bottom: 40px;
  }
  section > div:first-child {
    font-size: 1.55rem;
    font-style: normal;
    font-weight: 700;
    line-height: normal;
    letter-spacing: -0.04rem;
  }
  .questionContain {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }
  .questionContain > p {
    margin-top: 0;
  }
</style>