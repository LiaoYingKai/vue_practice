<template lang="html">
  <div class="change_button" >
    <div class="button" v-for="item in 10" v-on:click="changePage(item)" v-bind:class="{ now_page_style: isActive }">{{item}}</div>
  </div>
</template>

<script>
export default {
  methods: {
    changePage: function(index) {
      this.$emit("listToChange", index)
    }
  },
  data() {
    return {
      isActive: false,
      now_page: 1
    }
  }
}
</script>

<style lang="scss" scoped>
.change_button {
    display: flex;
    justify-content: center;
    margin-bottom: 50px;
    .button {
        padding: 10px;
        border: 1px solid transparent;
        cursor: pointer;
        margin: 0 10px;
        background-color: #fff;
        font-family: sans-serif;
        &:hover {
            border: 1px solid blue;
        }
    }
    .now_page_style {
        border-bottom: 1px solid blue;
    }
}
</style>
