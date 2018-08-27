<template>
<div id="app">
  <Header/>
  <Sildes/>
  <Lecturer/>
  <Intr/>
  <Footer/>
</div>
</template>

<script>
import Header from './components/header/Header'
import Sildes from './components/sildes/Sildes'
import Lecturer from './components/lecturer/Lecturer'
import Intr from './components/intr/Intr'
import Footer from './components/footer/Footer'


export default {
  name: 'App',
  components: {
    Header,
    Sildes,
    Lecturer,
    Intr,
    Footer
  }
}
</script>

<style >
body {
  margin: 0;
  padding: 0;
}
</style>
