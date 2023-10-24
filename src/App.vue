<template>
  <div id="app">
    <HeaderView></HeaderView>
    <ProgressView></ProgressView>
    <ContentView></ContentView>
  </div>
</template>

<script>
import HeaderView from './components/HeaderView.vue'
import ProgressView from './components/ProgressView.vue'
import ContentView from './components/ContentView.vue'

export default {
  name: 'App',
  components: { HeaderView, ProgressView, ContentView }
}
</script>

<style>
  @font-face {
    font-family: 'Pretendard-Regular';
    src: url('https://cdn.jsdelivr.net/gh/Project-Noonnu/noonfonts_2107@1.1/Pretendard-Regular.woff') format('woff');
    font-weight: 400;
    font-style: normal;
  }
  body, html {
    font-family: 'Pretendard-Regular';
    margin: 0; padding: 0;
    color: #222222;
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    letter-spacing: -0.0225rem;
  }
  * { text-decoration: none; }
  ul { margin: 0; padding: 0; }
  li { list-style: none; }
  label, main { display: block; }
  table { border-collapse: collapse;}

</style>
