<template>
<div class="main_content">
  <div class="content_text">
    <p class="main_content_title">
      {{title}}
    </p>
    <p class="main_content_sub_title">
      {{sub_title}}
    </p>
    <p v-for="content in contents">{{content.text}}</p>
    <div class="button">
      <button>{{button_text}}</button>
      <p class="button_subscript">{{button_subscript}}</p>
    </div>
  </div>
  <div class="content_image">
    <img src="../assets/download_pic.png" alt="hello" />
  </div>
</div>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      title: 'IDEAS?',
      sub_title: 'This is just a place holder.',
      button_text: 'TRY IT NOW!',
      button_subscript: 'Don\'t worry it\'s for free',
      contents: [{
        text: 'You can remove any link to our websitefrom this'
      }, {
        text: ' website template,you\'re free to use this website'
      }, {
        text: 'template without linking back to us'
      }],

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.main_content {
  width: 960px;
  margin: 40px auto;
  font-family: sans-serif;
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
}

.content_text {
  margin-left: 100px;
}

.main_content p {
  margin: 0;
  color: gray;
}


.main_content .main_content_title {
  font-size: 48px;
  color: #040404;
}

.main_content .main_content_sub_title {
  font-size: 24px;
  color: #040404;
}

.button {
  padding-left: 55px;
  padding-top: 20px;
}

button {
  color: #ffffff;
  font-size: 24px;
  border: none;
  text-align: center;
  display: inline-block;
  border-radius: 4px;
  padding: 15px 32px;
  background: -webkit-linear-gradient(90deg, rgba(255, 158, 74, 1)50%, rgba(255, 197, 91, 0.8)50%);
}

.button_subscript {
  margin: 0 auto;
  font-size: 4px;
  color: gray;
}
</style>
