<template lang="html">
  <div class="lecturer">
    <div class="title">
      {{title}}
    </div>
    <div class="lecturer_info">
      <p>{{lecturer_title}}</p>
      <div class="row">
        <div class="row_box" v-for="text in texts">
          <img v-bind:src="text.src" alt="">
          <h1>{{text.name}}</h1>
          <p>{{text.job_title}}</p>
        </div>
      </div>
      <div class="lecturer_button">
        {{button_text}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "lecturer",
  data() {
    return {
      title: "We design great websites and all sorts of interactive products from start to finish",
      lecturer_title: "Meet The Folks:",
      texts: [{
        src: require("../../assets/m1.jpg"),
        name: "Andreas",
        job_title: "Co Founder & Developer"
      }, {
        src: require("../../assets/m2.jpg"),
        name: "Matt",
        job_title: "Co Founder & Creative Director"
      }, {
        src: require("../../assets/m3.jpg"),
        name: "Dustin",
        job_title: "Desginer & Front End Developer"
      }, {
        src: require("../../assets/m4.jpg"),
        name: "Anna",
        job_title: "Desginer"
      }],
      button_text: "CONTACT US"
    }
  }
}
</script>

<style scoped lang="scss" src="./lecturer.scss">
</style>
