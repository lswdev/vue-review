
<template>
  <section>
    <div v-if="this.pagingNumber!=6">A/S 만족도 설문</div>
    <div class="sub-title" v-if="this.pagingNumber==1">
      홍길동 고객님 2023년 10월 25일 차량 A/S 수리는 잘 받으셨나요? 차량 수리에 대한 만족도 설문을 요청 드립니다.<br>
      설문 결과는 더 나은 서비스를 위한 기초 자료로 사용할 예정입니다. 감사합니다.
    </div>
    <div class="questionContain" v-if="this.pagingNumber!=6">
      <p>{{ this.pagingNumber==1 ? questionTitle : (this.pagingNumber==2 ? questionTitle2: (this.pagingNumber==3 ? questionTitle3: (this.pagingNumber==4 ? questionTitle4: questionTitle5))) }}</p>
      <ul class="questions" v-if="this.pagingNumber < 5">
        <li v-for="(item) in (this.pagingNumber==1 ? questionList : (this.pagingNumber==2 ? questionList2: (this.pagingNumber==3 ? questionList3: questionList4)))" :key="item.id">
          <input type="radio" :id="item.key" :value="item" name="radioGroup" @change="radioChange(item)" :checked="item.checked">
          <label :for="item.key">
            <span v-text="item.text"></span>
          </label>
        </li>
      </ul>
      <div class="textarea" v-if="this.pagingNumber == 5">
        <textarea placeholder="개선사항을 입력하세요"></textarea>
      </div>
    </div>
    <div class="complete" v-else>
      <div><img src="../assets/icons/check_circle.svg" alt="제출완료 아이콘"></div>
      <div>설문조사 제출이 완료되었습니다.</div>
    </div>
  </section>
</template>

<script>
  export default {
    props: {
      pagingNumber: {
        type: Number
      }
    },
    data: () => ({
      questionList: [
        { key: 'question01', text: '매우 상세하게 설명', checked: 'checked' },
        { key: 'question02', text: '비교적 상세하게 설명' },
        { key: 'question03', text: '일반적으로 설명' },
        { key: 'question04', text: '대충 설명함' },
        { key: 'question05', text: '설명 안함' },
      ],
      questionList2: [
        { key: 'question06', text: '정확하게 진행', checked: 'checked' },
        { key: 'question07', text: '조금 늦게 진행(10분 내)' },
        { key: 'question08', text: '다소 늦게 진행(30분 내)' },
        { key: 'question09', text: '매우 늦게 진행(1시간 내)' },
        { key: 'question10', text: '1시간 이상 지연됨' },
      ],
      questionList3: [
        { key: 'question11', text: '매우 청결함', checked: 'checked' },
        { key: 'question12', text: '비교적 청결함' },
        { key: 'question13', text: '보통' },
        { key: 'question14', text: '다소 어수선함' },
        { key: 'question15', text: '매우 지저분함' },
      ],
      questionList4: [
        { key: 'question16', text: '매우 친절하게 응대', checked: 'checked' },
        { key: 'question17', text: '비교적 친절하게 응대' },
        { key: 'question18', text: '보통' },
        { key: 'question19', text: '다소 불친절함' },
        { key: 'question20', text: '매우 불친절함' },
      ],
      questionTitle: '1. 수리기사는 수리 내용에 대해 상세하게 설명해 주었나요?',
      questionTitle2: '2. 예약된 방문 시간에 맞게 바로 수리가 진행되었나요?',
      questionTitle3: '3. 고객 대기실의 환경은 어떠하셨나요?',
      questionTitle4: '4. 고객 대기실의 직원은 친절하게 응대해 주었나요?',
      questionTitle5: '5. A/S 관련해서 개선할 사항을 적어주세요',
      picked: '',
      radioNm: 'radio01',
    }),
    mounted() {
      this.radioCheck();
    },
    watch: {
    },
    methods: {
      radioCheck() {
        document.querySelector('.questions > li > input:first-child').checked = 'checked';
      },
      radioChange(){//item
        // console.dir(item);
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
  section > div.sub-title, .questionContain > p {
    font-size: 1.5rem;
    font-weight: 400;
    line-height: 140%;
    letter-spacing: -0.03rem;
  }
  .questionContain {
    width: 100%;
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
  }
  .textarea {
    width: 100%;
  }
  .textarea textarea {
    width: 100%;
    height: 248px;
    border-radius: 0.3125rem;
    border-color: #D9D9D9;
    padding: 1.25rem;

    //color: #D9D9D9;
    font-family: Pretendard;
    font-style: normal;
    font-weight: 400;
    line-height: 140%;
    letter-spacing: -0.025rem;
  }
  .textarea textarea::placeholder {
    color: #D9D9D9;
  }

  /* complete */
  .complete {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 60px auto;
    gap: 2.75rem;
  }
</style>