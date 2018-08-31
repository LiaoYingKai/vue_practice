<template>
<div id="app">
  <Header v-bind:product="product"></Header>
  <Content v-bind:pagenumber="pagenumber" v-on:shoppingCart="shoppingCartInfo"></Content>
  <ChangePage v-on:listToChange="changePage"></ChangePage>
</div>
</template>

<script>
import Header from './components/Header'
import Content from './components/Content'
import ChangePage from './components/ChangePage'


export default {
  name: 'App',
  data() {
    return {
      pagenumber: 1,
      product: [{
        productName: "",
        productQuantity: "",
        productPrice: ""
      }],
      bottom: false
    }
  },
  watch: {
    bottom: function() {
      if (this.bottom) {
        this.pagenumber++;
        console.log(this.pagenumber);
        this.bottom = !this.bottom
      }
    }
  },
  components: {
    Header,
    Content,
    ChangePage
  },
  methods: {
    changePage: function(data) {
      this.pagenumber = data;
    },
    shoppingCartInfo: function(data) {
      this.product.push(data);
    },
    bottomVisible: function() {
      return document.documentElement.scrollHeight === (document.documentElement.scrollTop + document.documentElement.clientHeight);
    },
    addScrollEvent: function() {
      window.addEventListener("scroll", () => {
        this.bottom = this.bottomVisible();
      }, true)
    }
  },
  mounted() {
    // this.addScrollEvent();
  },
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
</style>
