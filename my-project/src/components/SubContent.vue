<template>
<div class="sub_content">
  <div class="sub_content_title">
    {{title}}
  </div>
  <div class="sub_content_text">
    <p v-for="text in texts">{{text.text}}</p>
  </div>
</div>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      title: "This is just a place holder.",
      texts: [{
          text: "You can remove any link to our website from this website template, you\'re free to use this website template without linking back to us."
        },
        {
          text: "This is just a place holder, so you can see what the site would look like."
        },
        {
          text: "You can remove any link to our website from this website template, you\'re free to use this website template without linking back to us. This is just a place holder, so you can see what the site would look like."
        },
        {
          text: "You can remove any link to our website from this website template, you\'re free to use this website template without linking back to us."
        },
        {
          text: "This is just a place holder, so you can see what the site would look like."
        },
        {
          text: "You can remove any link to our website from this website template, you're free to use this website template without linking back to us. This is just a place holder, so you can see what the site would look like."
        },
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.sub_content {
  width: 960px;
  margin: 40px auto;
  font-family: sans-serif;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.sub_content_title {
  margin-left: 100px;
  margin-bottom: 20px;
  font-size: 24px;
  color: #000000;
}

.sub_content_text {
  column-count: 2;
  column-gap: 80px;
  margin-left: 100px;

}

.sub_content_text p {
  color: gray;
  font-size: 16px;
  margin-top: 0;
}
</style>
