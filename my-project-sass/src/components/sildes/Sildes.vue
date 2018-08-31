<template>
<div class="slides">
  <div class="slides_background">
    <div class="slides_title">
      <h1>{{title}}</h1>
      <h2>{{sub_title}}</h2>
    </div>
    <p v-for="text in texts">{{text.text}}</p>
    <div class="slides_slgon">
      {{slgon_title}}
    </div>
  </div>
  <div class="slides_img">
    <div class="row">
      <div class="row_img" v-for="image in images">
        <img v-bind:src="image.src" alt="">
        <p>{{image.text}}</p>
      </div>
    </div>
  </div>
</div>
</template>

<script>
const path = require('path')
export default {
  name: "Header",
  computed: {
    images() {
      return this.imageData.map(url => {
        return {
          src: require(`../../${url}`),
          text: "test"
        }
      })
    }
  },
  data() {
    return {
      title: "WEB folk",
      sub_title: "Web Design Studio",
      texts: [{
        text: "We dream, explore, create and craft"
      }, {
        text: "progressive digital experiences"
      }, {
        text: "."
      }, {
        text: "."
      }, {
        text: "."
      }],
      slgon_title: "Work & Client",
      imageData: ["assets/p1.jpg",
        "assets/p2.jpg",
        "assets/p3.jpg",
        "assets/p4.jpg",
        "assets/p5.jpg",
        "assets/p6.jpg",
        "assets/p7.jpg",
        "assets/p8.jpg",
        "assets/p9.jpg",
        "assets/p10.jpg",
        "assets/p11.jpg",
        "assets/p12.jpg"
      ]
    }
  }
}
</script>

<style scoped src="./sildes.scss" lang="scss">
</style>
