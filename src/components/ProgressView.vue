
<template>
  <section>
    <ul class="progressContain">
      <li>
        <img :src="this.pagingNumber == 1 ? iconFirst: iconCheck" alt="icon-engineer">
        <div>수리기사</div>
      </li>
      <li :class="this.pagingNumber > 1 ? blueLine: ''"></li>
      <li>
        <img :src="this.pagingNumber > 2 ? iconCheck: (this.pagingNumber == 2 ? iconSecond : iconSecondGrey)" alt="icon-clock">
        <div>시간약속</div>
      </li>
      <li :class="this.pagingNumber > 2 ? blueLine: ''"></li>
      <li>
        <img :src="this.pagingNumber > 3 ? iconCheck: (this.pagingNumber == 3 ? iconThird : iconThirdGrey)" alt="icon-recycle">
        <div>대기환경</div>
      </li>
      <li :class="this.pagingNumber > 3 ? blueLine: ''"></li>
      <li>
        <img :src="this.pagingNumber > 4 ? iconCheck: (this.pagingNumber == 4 ? iconFourth : iconFourthGrey)" alt="icon-person">
        <div>응대수준</div>
      </li>
      <li :class="this.pagingNumber > 4 ? blueLine: ''"></li>
      <li>
        <img :src="this.pagingNumber > 5 ? iconCheck: (this.pagingNumber == 5 ? iconFifth : iconFifthGrey)" alt="icon-pages">
        <div>추가사항</div>
      </li>
    </ul>

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
      iconCheck: require('../assets/icons/icon-check.svg'),

      iconFirst: require('../assets/icons/icon-engineer.svg'),
      iconSecondGrey: require('../assets/icons/icon-clock-grey.svg'),
      iconSecond: require('../assets/icons/icon-clock.svg'),
      iconThirdGrey: require('../assets/icons/icon-recycle-grey.svg'),
      iconThird: require('../assets/icons/icon-recycle.svg'),
      iconFourthGrey: require('../assets/icons/icon-person-grey.svg'),
      iconFourth: require('../assets/icons/icon-person.svg'),
      iconFifthGrey: require('../assets/icons/icon-pages-grey.svg'),
      iconFifth: require('../assets/icons/icon-pages.svg'),

      blueLine: 'blue-line',
    }),
    watch: {
    },
    methods: {
    }
  }

</script>

<style scoped>
  section {
    margin: 40px auto 80px;
    padding: 40px 0 10px;
    width: 1150px;
  }
  .progressContain {
    display: flex;
    flex-flow: row nowrap;
    justify-content: center;
    align-items: center;
  }
  .progressContain > li:nth-of-type(odd) {
    width: 60px;
    height: 60px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
  }
  .progressContain > li:nth-of-type(even) {
    width: 96px;
    height: 10px;
    background: #F5F5F5;
  }
  .progressContain > li > div {
    white-space: nowrap;
  }
  .blue-line {
    background-color: #1890FF !important;
  }
</style>