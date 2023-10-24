
<template>
  <section>
    <ul class="progressContain">
      <li>
        <img :src="iconFirst" alt="icon-engineer">
        <div>수리기사</div>
      </li>
      <li></li>
      <li>
        <img :src="iconSecond" alt="icon-clock">
        <div>시간약속</div>
      </li>
      <li></li>
      <li>
        <img :src="iconThird" alt="icon-recycle">
        <div>대기환경</div>
      </li>
      <li></li>
      <li>
        <img :src="iconFourth" alt="icon-person">
        <div>응대수준</div>
      </li>
      <li></li>
      <li>
        <img :src="iconFifth" alt="icon-pages">
        <div>추가사항</div>
      </li>
    </ul>

  </section>
</template>

<script>
  export default {
    data: () => ({
      iconFirst: require('../assets/icons/icon-engineer.svg'),
      iconSecond: require('../assets/icons/icon-clock-grey.svg'),
      iconThird: require('../assets/icons/icon-recycle-grey.svg'),
      iconFourth: require('../assets/icons/icon-person-grey.svg'),
      iconFifth: require('../assets/icons/icon-pages-grey.svg'),
    }),
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
</style>