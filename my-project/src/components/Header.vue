<template>
<div class="header">
  <div class="nav">
    <ul>
      <li>
        <img src="../assets/logo_icon.png" alt="hello" />
      </li>
      <li v-for="item in nav_tag">
        <a href="#">{{item.text}}</a>
      </li>
    </ul>
  </div>
</div>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      message: "test",
      nav_tag: [{
        text: "Home"
      }, {
        text: "Features"
      }, {
        text: "News"
      }, {
        text: "About"
      }, {
        text: "Content"
      }]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  background-color: #eeeeef;
}

.nav {
  background-color: #eeeeef;
  width: 960px;
  margin: 0 auto;
}

.nav ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.nav a {
  font-family: sans-serif;
  size: 8px;
  margin-left: 80px;
  text-decoration: none;
  color: #9e9e9e;
}
</style>
