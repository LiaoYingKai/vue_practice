<template lang="html">
  <div class="content">
    <ul>
      <li v-for="item in text">
        <div class="image">
          <img :src="`https://f.ecimg.tw${item.picS}`" alt="" >
        </div>
        <div class="content_text">
          <p class="title" >產品名稱：{{item.name}}</p>
          <p class="describe">產品介紹：{{item.describe}}</p>
        </div>
        <div class="price_content">
          <p class="price">原價：<span>{{item.price}}</span></p>
          <p class="origin_price" v-if="show">特價：{{item.originPrice}}</p>
          <input type="number" min="0" max="10" v-model="item.quantity">
          <button v-on:click="intoShoopingCart(item.name,item.quantity,item.price)">加入購物車</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      text: [],
      show: false,
    }
  },
  props: ["pagenumber"],
  watch: {
    pagenumber: function() {
      this.showProduct(this.pagenumber)
    }
  },
  // updated: function() {
  //   this.$nextTick(function() {
  //     this.showProduct(this.pagenumber)
  //   })
  // },
  methods: {
    intoShoopingCart: function(name, number, price) {
      let product = {
        productName: name,
        productQuantity: number,
        productPrice: price
      }
      this.$emit("shoppingCart", product)
    },
    showProduct: function(pagenumber) {
      axios.get(`https://cors-anywhere.herokuapp.com/https://ecshweb.pchome.com.tw/search/v3.3/all/results?page=${pagenumber}&q=apple&sort=rnk/dc`)
        .then(response => {
          // this.text = response.data.prods;
          this.text.push(...response.data.prods);
          this.text.forEach(item => item["quantity"] = 0)
        })
        .catch(error => {
          console.log("Error: " + error)
        })
    }
  },

  mounted: function() {
    this.showProduct(this.pagenumber);
  },
}
</script>

<style lang="scss" scoped>
.content {
    width: 80%;
    margin: 0 auto;
    background-color: #fffbed;
}
p {
    margin: 0;
    font-family: sans-serif;
}
ul {
    padding: 0;
    display: flex;
    flex-wrap: wrap;
    list-style: none;
}
ul li {
    display: flex;
    border-bottom: 1px solid gray;
}
.image {
    display: flex;
    justify-content: center;
    align-items: center;
    min-width: 15vw;
    img {
        width: 80%;
        height: 80%;
    }
}

.content_text {
    display: flex;
    justify-content: center;
    flex-direction: column;
    .describe {
        display: -webkit-box;
        -webkit-box-orient: vertical;
        -webkit-line-clamp: 3;
        overflow: hidden;
    }
}

.price_content {
    min-width: 10vw;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    span {
        font-size: 28px;
        color: #fe5b77;
    }
    input {
        width: 50%;
        margin: 10px;
    }
}
</style>
