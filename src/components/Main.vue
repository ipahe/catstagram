<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <a class="navbar-brand" href="#">Catstagram</a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto"></ul>
        <form class="form-inline my-2 my-lg-0">
          <input
            class="form-control mr-sm-2"
            type="search"
            placeholder="Buscar"
            aria-label="Search"
          >
          <button class="btn btn-outline-success my-2 my-sm-0" type="button">Buscar</button>
        </form>
      </div>
    </nav>
    <section class="posts">
      <div class="container">
        <div class="row">
          <Post v-for="(catImage, index) in catsArray" :cat="catImage" :key="catImage.id"/>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Post from "./Post";
export default {
  name: "Main",
  components: {
    Post
  },
  data() {
    return {
      apiURL: "https://api.thecatapi.com/v1",
      catsArray: []
    };
  },
  mounted() {
    //Add defatult token header to every request
    $.ajaxSetup({
      headers: { "x-api-key": "ea268ab2-5313-46d5-8b53-7f6a48f4f2ff" }
    });

    //Get initiall data
    $.get(`${this.apiURL}/images/search`, { limit: 9, size: 300 }, response => { this.catsArray = response; });

    window.onscroll = () => {
      let bottomOfWindow = document.documentElement.scrollTop + window.innerHeight === document.documentElement.offsetHeight;
      if (bottomOfWindow) {
        $.get(`${this.apiURL}/images/search`, { limit: 6, size: 300 }, response => { 
          response.forEach(cat => { this.catsArray.push(cat) });            
        });
      }
    };
  },
  methods: {

  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.posts {
  padding-top: 20px;
}

.post-wrapper {
  padding-bottom: 20px;
}
</style>
