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
          <div class="form-group pr-2">
            <label for="catBreeds">Buscar por raza: &nbsp;</label>
            <select class="form-control" id="catBreeds" v-model="searchParam" v-on:change="breedSelected">
              <option ></option>
              <option v-for="breed in catBreeds" :key="breed.id" :value="breed.id">{{ breed.name }}</option>
            </select>
          </div>
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
      catsArray: [],
      catBreeds: [],
      searchParam: ''
    };
  },
  mounted() {
    //Add defatult token header to every request
    $.ajaxSetup({
      headers: { "x-api-key": "ea268ab2-5313-46d5-8b53-7f6a48f4f2ff" },
      cache: false
    });

    //Get initiall data
    $.get(`${this.apiURL}/images/search`, { limit: 9, size: 300 }, response => { this.catsArray = response; });
    $.get(`${this.apiURL}/breeds`, { }, response => { this.catBreeds = response; });

    window.onscroll = () => {
      let bottomOfWindow = document.documentElement.scrollTop + window.innerHeight === document.documentElement.offsetHeight;
      if (bottomOfWindow) {

        if(this.searchParam.length > 0){
          $.get(`${this.apiURL}/images/search?breed_ids=${this.searchParam}&limit=6`, { limit: 6, size: 300 }, response => { 
            response.forEach(cat => { this.catsArray.push(cat) });            
          });
        }else{
          $.get(`${this.apiURL}/images/search`, { limit: 6, size: 300 }, response => { 
            response.forEach(cat => { this.catsArray.push(cat) });            
          });
        }
      }
    };
  },
  methods: {
    breedSelected: function() {
      $.get(`${this.apiURL}/images/search?breed_ids=${this.searchParam}&limit=9`, { }, response => { this.catsArray = response; });
    }
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
