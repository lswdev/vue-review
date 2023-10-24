
<template>
  <header>
    <div class="logoContain"><img src="../assets/logo.png" alt="logo"></div>
  </header>
</template>

<script>
  export default {

  }
</script>

<style scoped>
  header {
    background-color: #1e1e2d;
    padding: 0.8rem 1.5rem;
    margin: 40px auto;
    width: 1150px;
    display: flex;
    align-items: center;
    flex-shrink: 0;
    border-radius: 0.625rem;
  }
  header > div.logoContain {

  }
  header > div:first-of-type > img {
    width: 10rem;
    object-fit: cover;
  }
</style>