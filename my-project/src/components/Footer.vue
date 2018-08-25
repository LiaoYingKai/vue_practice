<template>
<div class="footer">
  <div class="footer_content">
    <div class="footer_text">
      {{text}}
    </div>
    <div class="footer_logo">
      <img src="../assets/facebook_icon.png" alt=" ">
      <img src="../assets/google_icon.png" alt=" ">
      <img src="../assets/twitter_icon.png" alt=" ">
      <img src="../assets/pinterest_icon.png" alt=" ">
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      text: "© 2023 Zerotype.All Right Ressrved."
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.footer {

  width: 100%;
  height: 75px;
  background-color: #eeeeef;
  position: fixed;
  bottom: 0px;
}

.footer_content {
  width: 960px;
  margin: 0 auto;
  line-height: 75px;
  display: flex;
  justify-content: space-between;
}

.footer_text {
  color: #2b2a2a;
  font-size: 8px;
}

.footer_logo {
  display: flex;
  align-items: center;
}

.footer_logo img {
  margin-left: 10px;
}
</style>
