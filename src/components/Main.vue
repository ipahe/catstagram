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
          <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Buscar</button>
        </form>
      </div>
    </nav>
    <section class="posts">
      <div class="container">
        <div class="row">
          <div class="col-sm-4 post-wrapper">
            <div class="post">
              <img class="img-fluid blog-img" src="http://www.themashabrand.com/templates/Masha/Medium/img/blog/9.jpg" alt="blog image">
            </div>
          </div>
		  <div class="col-sm-4 post-wrapper">
            <div class="post">
              <img class="img-fluid blog-img" src="http://www.themashabrand.com/templates/Masha/Medium/img/blog/9.jpg" alt="blog image">
            </div>
          </div> 
		  <div class="col-sm-4 post-wrapper">
            <div class="post">
              <img class="img-fluid blog-img" src="http://www.themashabrand.com/templates/Masha/Medium/img/blog/9.jpg" alt="blog image">
            </div>
          </div> 
		  <div class="col-sm-4 post-wrapper">
            <div class="post">
              <img class="img-fluid blog-img" src="http://www.themashabrand.com/templates/Masha/Medium/img/blog/9.jpg" alt="blog image">
            </div>
          </div> 
		  <div class="col-sm-4 post-wrapper">
            <div class="post">
              <img class="img-fluid blog-img" src="http://www.themashabrand.com/templates/Masha/Medium/img/blog/9.jpg" alt="blog image">
            </div>
          </div> 
		  <div class="col-sm-4 post-wrapper">
            <div class="post">
              <img class="img-fluid blog-img" src="http://www.themashabrand.com/templates/Masha/Medium/img/blog/9.jpg" alt="blog image">
            </div>
          </div> 
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "Main",
  data() {
    return {};
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.posts {
  padding-top: 20px;
}

.post-wrapper{
	padding-bottom: 20px;
}
</style>
