<template>
  <div class="col-sm-4 post-wrapper">
    <div class="post">
      <a href="javascript:;" v-on:click="showFullImage">
        <img
          class="img-fluid blog-img"
          :src="image"
          alt="blog image"
        >
      </a>
    </div>
    <!-- Modal -->
    <div
      class="modal fade"
      id="exampleModal"
      tabindex="-1"
      role="dialog"
      aria-labelledby="exampleModalLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div class="modal-body">
            <img
              class="img-fluid blog-img"
              :src="image"
              alt="blog image"
            >
          </div>
          <div class="modal-footer"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Post",
  props: ['image'],
  data() {
    return {};
  },
  methods: {
    showFullImage: function() {
      $("#exampleModal").modal();
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
