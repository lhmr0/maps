<template>
  <section>
    <section class="hero is-dark is-fullheight">
    <div class="hero-body">
    <div class="container">
      <h1 class="title">
      Welcome
      </h1>
      <h2 class="subtitle">
      SEARCH AND RATE
      </h2>
      <b-autocomplete  v-model="name" :data="data" placeholder="Search a movie title..." icon="search" field="title" :loading="isFetching" @input="getAsyncData" @select="option => selected = option">
          <template scope="props" >
            <div class="media" @click="mensaje(props.option.movie.value)">
              <div class="media-left">
                <img width="32" v-if="props.option.image" :src="`${props.option.image.value}`">
              </div>
              <div class="media-content">
                {{ props.option.movieLabel.value }}
                <br>
                <small v-if="props.option.movieYear && props.option.movieDuration" >
                 Released at {{ props.option.movieYear.value }}, 
                 runtime {{ props.option.movieDuration.value }}</b>
                 </small>
              </div>
            </div>
          </template>
        </b-autocomplete>
    </div>
    </div>
  </section> 
    
</section>




   
 


</template>


<script>
  
</script>


<style scoped>
  .hero {
    background-image:url(https://luishmr0.github.io/semanticmovies/img/bg.jpg);
    background-repeat:no-repeat;
    background-attachment:scroll;
    background-position:center center;
    -webkit-background-size:cover;
    -moz-background-size:cover;
    -o-background-size:cover;
    background-size:cover;    
  }
</style>
