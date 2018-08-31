<template lang="html">
<div class="header">
  <ul >
    <li v-on:click="test">
      {{shoppingCart}}
    </li>
    <li>
      {{login}}
    </li>
    <li>
      {{logout}}
    </li>
  </ul>
  <div class="shoppingCartShow" v-if="show" v-for="item in product">
    商品名稱：{{item.productName}}
    購買數量：{{item.productQuantity}}
    商品價格：{{item.productPrice}}
    小計：{{item.productQuantity*item.productPrice}}
  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      shoppingCart: "ShoppingCart",
      login: "login",
      logout: "Logout",
      show: false
    }
  },
  props: ["product"],
  methods: {
    test: function() {
      this.show = !this.show;
    }
  }
}
</script>

<style scoped lang="scss">
.header {
    background-color: gray;
}
ul {
    list-style: none;
    display: flex;
    margin: 0;
    padding: 0;
    li {
        margin: 20px;
        font-family: sans-serif;
        &:hover {
            cursor: pointer;
        }
    }
}
.shoppingCartShow {
    background-color: #fff;
    font-family: sans-serif;
    padding: 10px 30px;
    font-size: 18px;
}
</style>
