<template>
  <div class="col-sm-4 post-wrapper">
    <div class="post">
      <a href="javascript:;" @click="catClicked">
        <img class="img-fluid blog-img" :src="cat.url" alt="Cat image">
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "Post",
  props: ["cat"],
  data() {
    return {};
  },
  methods: {
    catClicked: function() {
      this.$emit("cat-clicked", this.cat);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.post-wrapper {
  padding-bottom: 20px;
}
</style>
