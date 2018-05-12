<template>
  <div id="app">
    <appHeader/>
    <router-view/>
    <appFooter/>
  </div>
</template>

<script>
import Header from '@/components/Header';
import Footer from '@/components/Footer';

export default {
  name: 'App',
  components: {
    appHeader: Header,
    appFooter: Footer,
  },
};
</script>

<style>
body, html {
  padding: 0;
  margin: 0;
}
body {
  background: #f4f4f4;
  overflow: scroll !important;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
