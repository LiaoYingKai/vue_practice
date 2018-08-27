<template>
<div class="header">
  <ul>
    <li v-for="item in items">
      <a href="#">{{item.text}}</a>
    </li>
  </ul>
</div>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      items: [{
        text: "Home"
      }, {
        text: "Contact"
      }]
    }
  }
}
</script>

<style scoped src="./header.scss" lang="scss"></style>
