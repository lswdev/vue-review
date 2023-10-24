<template>
  <div id="app">
    <HeaderView></HeaderView>

  </div>
</template>

<script>
import HeaderView from './components/HeaderView.vue'

export default {
  name: 'App',
  components: { HeaderView }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}

body, html { margin: 0; padding: 0; }
* { text-decoration: none; }
ul { margin: 0; padding: 0; }
li { list-style: none; }
label, main { display: block; }
table { border-collapse: collapse;}

</style>
