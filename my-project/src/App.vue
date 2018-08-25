<template>
<div id="app">
  <Header/>
  <MainContent/>
  <SubContent/>
  <Footer/>
</div>
</template>

<script>
import Header from './components/Header'
import MainContent from './components/MainContent'
import SubContent from './components/SubContent'
import Footer from './components/Footer'


export default {
  name: 'App',
  components: {
    Header,
    MainContent,
    SubContent,
    Footer
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
</style>
