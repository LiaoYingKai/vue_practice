<template lang="html">
  <div class="footer">
      <p>{{text}}<span>{{span_text}}</span></p>
    </div>
</template>

<script>
export default {
  name: "Footer",
  data() {
    return {
      text: "@ 2023 by Web Folk. Proudly created with ",
      span_text: "Wix.com"
    }
  }
}
</script>

<style scoped lang="scss" src="./footer.scss">
</style>
