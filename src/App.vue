<template>
  <div id="app">
    <HeaderView></HeaderView>
    <ProgressView :pagingNumber="pages"></ProgressView>
    <ContentView :pagingNumber="pages"></ContentView>
    <FooterView @paging="paging"></FooterView>
  </div>
</template>

<script>
import HeaderView from './components/HeaderView.vue'
import ProgressView from './components/ProgressView.vue'
import ContentView from './components/ContentView.vue'
import FooterView from './components/FooterView.vue'

export default {
  name: 'App',
  data:() => ({
    pages: 1,
  }),
  components: { HeaderView, ProgressView, ContentView, FooterView },
  methods: {
    paging(value) {
      this.pages = value;
    }
  }
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
    user-select: none;
  }
  * { text-decoration: none; }
  ul { margin: 0; padding: 0; }
  li { list-style: none; }
  label, main { display: block; }
  table { border-collapse: collapse;}

</style>
