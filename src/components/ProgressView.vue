
<template>
  <section>
    <ul class="progressContain">
      <li>
        <div></div>
        <div></div>
      </li>
      <li>2</li>
      <li>
        <div></div>
        <div></div>
      </li>
      <li>4</li>
      <li>
        <div></div>
        <div></div>
      </li>
      <li>6</li>
      <li>
        <div></div>
        <div></div>
      </li>
      <li>8</li>
      <li>
        <div></div>
        <div></div>
      </li>
    </ul>
  </section>
</template>

<script>

</script>

<style scoped>
  section {
    margin: 40px auto;
    width: 1150px;
    border: 1px solid red;
    box-sizing: border-box;
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
    background-color: yellow;
  }
  .progressContain > li:nth-of-type(even) {
    width: 96px;
    height: 10px;
    background-color: green;
  }
</style>