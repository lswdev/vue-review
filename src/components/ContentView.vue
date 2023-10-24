
<template>
  <section>
    <div>A/S 만족도 설문</div>
    <div>
      홍길동 고객님 2023년 10월 25일 차량 A/S 수리는 잘 받으셨나요? 차량 수리에 대한 만족도 설문을 요청 드립니다.<br>
      설문 결과는 더 나은 서비스를 위한 기초 자료로 사용할 예정입니다. 감사합니다.
    </div>
    <div class="questionContain">
      <p>{{ questionTitle }}</p>
      <ul class="questions">
        <li v-for="(item) in (this.paging==1 ? questionList : questionList2)" :key="item.id">
          <input type="radio" :id="item.key" :value="item" name="radioGroup">
          <label :for="item.key">
            <span v-text="item.text"></span>
          </label>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
  export default {
    data: () => ({
      questionList: [
        { key: 'question01', text: '매우 상세하게 설명' },
        { key: 'question02', text: '비교적 상세하게 설명' },
        { key: 'question03', text: '일반적으로 설명' },
        { key: 'question04', text: '대충 설명함' },
        { key: 'question05', text: '설명 안함' },
      ],
      questionList2: [
        { key: 'question06', text: '정확하게 진행' },
        { key: 'question07', text: '조금 늦게 진행(10분 내)' },
        { key: 'question08', text: '다소 늦게 진행(30분 내)' },
        { key: 'question09', text: '매우 늦게 진행(1시간 내)' },
        { key: 'question10', text: '1시간 이상 지연됨' },
      ],
      questionTitle: '1. 수리기사는 수리 내용에 대해 상세하게 설명해 주었나요?',
      picked: '',
      radioNm: 'radio01',
      paging: 1,
    }),
    mounted() {
      this.radioCheck();
    },
    watch: {
    },
    methods: {
      radioCheck() {
        document.querySelector('.questions > li > input:first-child').checked = 'checked';
      }
    },
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
    font-size: 2rem;
    font-style: normal;
    font-weight: 700;
    line-height: normal;
    letter-spacing: -0.04rem;
  }
  section > div:nth-of-type(2), .questionContain > p {
    font-size: 1.5rem;
    font-weight: 400;
    line-height: 140%;
    letter-spacing: -0.03rem;
  }
  .questionContain {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }
  .questionContain > p {
    margin-top: 0;
    margin-bottom: 40px;
  }
  .questions > li {
    margin-bottom: 1rem;
    display: flex;
    align-items: center;
  }
  .questions > li label {
    cursor: pointer;
  }
  .questions > li span {
    padding-left: 0.8rem;
  }
  input[type="radio"] {
    width: 20px;
    height: 20px;
    cursor: pointer;
    -webkit-appearance: none;
    -moz-appearance: none;
    border: 1px solid #eee;
    border-radius: 100%;
  }
  input[type="radio"]:checked {
    border: 3px solid #1890FF;
    border-radius: 100%;
  }
</style>