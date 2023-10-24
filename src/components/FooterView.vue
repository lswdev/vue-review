
<template>
  <footer>
    <div class="pagination">
      <button style="background-color: #FFF; color:#1890FF;" @click="prevClick" v-if="pageNm > 1"><img src="../assets/icons/arrow_back.svg" alt="이전"> 이전</button>
      <button style="background-color: #1890FF; color:#FFF;" @click="nextClick">다음 <img src="../assets/icons/arrow_forward.svg" alt="다음"></button>
    </div>
  </footer>
</template>

<script>
  export default {
    data: () => ({
      pageNm: 1,
    }),
    methods: {
      prevClick(){
        if(this.pageNm > 1) {
          this.pageNm -= 1;
        }
        this.$emit("paging", this.pageNm);
      },
      nextClick(){
        if(this.pageNm < 6) {
          this.pageNm += 1;
        }
        this.$emit("paging", this.pageNm);
      }
    }
  }
</script>

<style scoped>
  footer {
    margin: 100px auto 0;
    width: 1150px;
  }
  .pagination {
    display: flex;
    flex-flow: row nowrap;
    gap: 1rem;
    float: right;
  }
  .pagination > button {
    display: flex;
    align-items: center;
    border-radius: 6.25rem;
    border: 1px solid #1890FF;
    padding: 0.225rem 1.1rem;
    gap: 0.225rem;
    font-size: 1.15rem;
    font-weight: 700;
    cursor: pointer;
  }
</style>